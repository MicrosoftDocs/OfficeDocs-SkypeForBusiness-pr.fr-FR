---
title: Réunions, webinaires et événements en direct
ms.reviewer: ''
description: Un guide destiné aux administrateurs pour déployer et configurer des réunions, des webinaires et des événements en direct dans Microsoft Teams.
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
ms.openlocfilehash: ffd0ad9f9b765839a4543dd8600b558000fa164f
ms.sourcegitcommit: abe942c294ed5fca70efdf039d38d611b9c21fe9
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2022
ms.locfileid: "63564736"
---
# <a name="meetings-webinars-and-live-events"></a>Réunions, webinaires et événements en direct 

Il existe plusieurs façons de se réunir dans Microsoft Teams : réunions, webinaires et événements en direct. 

Cet article, destiné aux administrateurs et aux professionnels de l'informatique, décrit les différences entre les réunions, les webinaires et les événements en direct. Il fournit ensuite des liens vers les informations dont vous avez besoin pour déployer rapidement cette fonctionnalité pour vos utilisateurs.

> [!Note]
> Pour plus d’informations sur la configuration rapide de réunions et d’événements Teams sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).


[Les réunions](#meetings), [les webinaires](#webinars) et [les événements en direct](#live-events) sont tous des types de réunions, mais les webinaires et les événements en direct offrent à l'organisateur un contrôle supplémentaire sur la conversation et les participants. Les webinaires permettent une interaction bidirectionnelle tandis que les événements en direct offrent une expérience de questions-réponses gérée. 

Les différents types de réunions ont également des limites de participants et des fonctionnalités de participants différentes. 

Le tableau suivant résume les trois types de réunions, le nombre de participants recommandé et la manière dont les participants peuvent interagir dans la réunion. Des sections contenant plus d'informations sur chaque type de réunion suivent le tableau. Cet article comprend également une section sur [les meilleures pratiques pour les grandes réunions](#best-practices-for-large-meetings).
<br><br>

| Type de réunion | Nombre de participants | Interaction | Inscription prise en charge |
|----------|--------|--------|-----|
| Réunions  | Jusqu’à 20 000* <br> | - Jusqu’à 1 000, les participants disposent des mêmes fonctionnalités de réunion totalement interactives. <br> - Au delà de 1 000 et jusqu’ à 20 000, les participants ont des fonctionnalités en [lecture seule](view-only-meeting-experience.md).  | Non |
| Séminaires web | - Jusqu'à 1 000<br>- Des limites accrues avec des fonctionnalités en [lecture seule](view-only-meeting-experience.md) seront bientôt disponibles. |- Jusqu’à 1 000, les participants disposent de fonctionnalités totalement interactives. <br> -Interaction de l’audience configurable. <br> - Peut spécifier des présentateurs. | Oui |
| Événements en direct | Jusqu’à 20 000** |- Diffuser au grand public. <br>- Questions et réponses modérées pour l’interaction de l’audience. <br> - Peut spécifier des producteurs et des présentateurs, y compris des présentateurs externes.<br>- Prend en charge des fonctionnalités de production plus avancées. | Non |
||||

*Les 10 000 habituels sont augmentés à 20 000 jusqu’au 30 juin 2022.<br>

**Les 10 000 habituels sont augmentés à 20 000 jusqu’au 30 juin 2022. Vous pouvez planifier des nombres encore plus importants avec des événements en direct dans Yammer et/ou Microsoft Stream. Pour plus d’informations, consultez [Événements en direct sur Microsoft 365](/stream/live-event-m365). Notez que les événements de plus de 20 000 participants nécessitent le [Programme d’assistance aux événements en direct](/stream/live-events-assistance). 

Notez que NDI est entièrement pris en charge dans les réunions, les webinaires et les événements en direct, ce qui vous permet de produire la diffusion en utilisant des outils tels que OBS et Wirecast. Pour plus d'informations, voir [Utiliser la technologie NDI® dans Microsoft Teams](use-ndi-in-meetings.md).

## <a name="meetings"></a>Réunions

**Les réunions** dans Teams incluent le partage audio, vidéo et d’écran pour jusqu’à 1 000 personnes et des [fonctionnalités d’affichage uniquement](view-only-meeting-experience.md) pour les événements de plus de 1 000 participants. Les participants n’ont pas besoin d’être membres d’une organisation (ou d’avoir un compte Teams) pour participer à une réunion Teams. Ils peuvent participer directement à partir de l’invitation au calendrier via le lien Rejoindre la réunion ou appeler via audio, le cas échéant.  

En tant qu’administrateur, vous allez configurer les paramètres de réunion et contrôler les fonctionnalités de réunion activées pour votre organisation en spécifiant des stratégies de réunion.  

Outre les réunions planifiées régulièrement, vos utilisateurs peuvent créer des réunions de canal. Avec les réunions de canal, tous les membres d’une équipe peuvent voir qu’il y a une réunion, participer à la réunion et utiliser la conversation de réunion. Les réunions de canal permettent d’inviter rapidement tous les membres d’une équipe à une réunion. Pour plus d’informations sur la façon dont les utilisateurs finaux planifient des réunions, consultez [Planifier une réunion](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5).

Pour plus d’informations sur l’expérience de réunion en lecture seule, consultez [Expérience de réunion en lecture seule Teams](view-only-meeting-experience.md).

### <a name="articles-for-administrators"></a>Articles pour les administrateurs

Le tableau suivant met en évidence les articles clés que vous souhaitez examiner :

| Article | Description | 
|----------|--------|
| [Paramètres de réunion](meeting-settings-in-teams.md) |  Décrit comment configurer les paramètres des réunions pour les utilisateurs anonymes, les invitations aux réunions et le trafic multimédia.  |
| [Stratégies de réunion](meeting-policies-overview.md)  | Décrit comment créer et gérer les stratégies qui déterminent les fonctionnalités disponibles pour les participants à la réunion. | 
| [Gérer l’enregistrement des réunions cloud Teams](cloud-recording.md) | Décrit comment gérer les enregistrements de réunion. |
| [Gérer les appareils de votre organisation](device-management.md)| Décrit comment gérer les appareils de votre organisation, tels que les téléphones et les salles Teams. |
| [Utiliser la télémétrie en temps réel pour résoudre les problèmes de qualité des réunions](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md) | Décrit comment utiliser RTA (Real-Time Analytics) pour résoudre des problèmes de qualité des réunions Microsoft Teams pour des utilisateurs individuels. 
|||

### <a name="key-training-for-end-users"></a>Formation clé pour les utilisateurs finaux

Le tableau suivant répertorie les formations disponibles pour les utilisateurs finaux de votre organisation :

| Formation | Description | 
|----------|--------|
| [Gérer les réunions](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) | Vidéo de formation rapide destinée aux utilisateurs qui débutent avec les réunions Teams. |
| [Planifier une réunion](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5) | Article qui décrit comment planifier différents types de réunions. |
| [Tenez des réunions efficaces avec Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings) | Classe gratuite dirigée par un instructeur sur la façon de rendre les réunions plus attrayantes, productives et significatives. |
| [Modifier les paramètres des participants pour une réunion Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) | Article sur la gestion des options de réunion.
||


## <a name="webinars"></a>Séminaires web

**Les webinaires** sont des réunions structurées où les présentateurs et les participants ont des rôles clairs. Une différence clé entre les webinaires et les réunions Teams est que les webinaires prennent en charge l’inscription et fournissent des données d’engagement des participants. Pour activer les webinaires dans votre organisation, consultez [Configurer des webinaires dans Teams](set-up-webinars.md). 


### <a name="key-training-for-end-users"></a>Formation clé pour les utilisateurs finaux

Le tableau suivant répertorie les formations disponibles pour les utilisateurs finaux de votre organisation :

| Formation | Description | 
|----------|--------|
| [Démarrage avec les webinaires Teams](https://support.microsoft.com/office/get-started-with-teams-webinars-42f3f874-22dc-4289-b53f-bbc1a69013e3) | Vidéo de formation rapide destinée aux utilisateurs qui débutent avec les webinaires Teams. |
| [Guide de démarrage rapide visuel](https://adoption.microsoft.com/files/assets/TeamsWebinarsGetStartedGuide.pdf) | Guide visuel téléchargeable qui décrit comment commencer à planifier des webinaires.  |
||


## <a name="live-events"></a>Événements en direct

**Les événements en direct** sont des réunions structurées qui permettent à votre organisation de planifier et de produire des événements qui sont diffusés en continu à de grands publics en ligne&mdash; jusqu’à 20 000 personnes. Avec les événements en direct, l’interaction de l’audience est une expérience de questions et réponses managée.

### <a name="articles-for-administrators"></a>Articles pour les administrateurs

Le tableau suivant met en évidence les articles clés que vous souhaitez examiner :

| Article | Description | 
|----------|--------|
| [Que sont les événements en direct Teams ?](teams-live-events/what-are-teams-live-events.md)  | Présentation rapide des événements en direct. |
| [Offre pour les événements en direct Teams](teams-live-events/plan-for-teams-live-events.md) | Ce que vous devez savoir avant de configurer des événements en direct. |
| [Configurer les événements en direct Teams](teams-live-events/set-up-for-teams-live-events.md) | Décrit les prérequis, tels que la planification réseau. |
| [Configurer des événements en direct](teams-live-events/configure-teams-live-events.md) | Étapes de configuration des événements en direct.
||

### <a name="key-training-for-end-users"></a>Formation clé pour les utilisateurs finaux

Le tableau suivant répertorie les formations disponibles pour les utilisateurs finaux de votre organisation :

| Formation | Description | 
|----------|--------|
| [Démarrage avec les événements en direct](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a) | Présentation des événements en direct et de la prise en main. |
| [Formation vidéo sur les événements en direct Teams](https://support.microsoft.com/en-us/office/plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502?ui=en-US&rs=en-US&ad=US) | Vidéo qui décrit comment organiser et planifier un événement en direct.  |
||

Pour produire des événements virtuels à plus grande échelle, consultez le [Guide Événement Virtuel](https://adoption.microsoft.com/virtual-event-guidance/), qui contient des conseils pour les organisateurs d’événements, les producteurs techniques, les professionnels de l’informatique et les créateurs de contenu. 

## <a name="apps-for-meetings"></a>Applications pour les réunions

Microsoft vous permet d'améliorer les expériences de réunion en intégrant et en utilisant des applications de réunion. Par exemple, l'intégration d'un tableau blanc dans les réunions Teams est assurée par l'application Web Whiteboard, qui permet aux participants aux réunions Teams de dessiner, d'esquisser et d'écrire ensemble sur une toile numérique partagée.

Vous pouvez ajouter des applications de réunion à votre déploiement Teams à l’aide des applications fournies avec Teams, à l’aide d’applications et de modèles tiers certifiés, et en créant vos propres applications personnalisées. 

Le tableau suivant répertorie les articles pour plus d’informations :

| Article | Description | 
|----------|--------|
| [Applications, bots et connecteurs](deploy-apps-microsoft-teams-landing-page.md) | Présentation des applications et comment déployer des applications pour votre organisation. |
| [Applications pour les réunions Teams](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings) | Vue d’ensemble de l’extensibilité des applications de réunion, des références d’API et de la façon d’activer et de configurer des applications pour les réunions. |
| [Gérer le tableau blanc dans Teams](manage-whiteboard.md) | Décrit les fonctionnalités du Tableau blanc et comment l’activer et désactiver pour votre organisation. |
||

## <a name="license-requirements-for-meetings-webinars-and-live-events"></a>Licence requise pour les réunions, les webinaires et les événements en direct

Tout le monde peut assister gratuitement à une réunion d'équipe, un webinaire ou un événement public en direct, &mdash;sans licence. 

Pour les personnes qui organisent, planifient et hébergent des réunions, des webinaires ou des événements en direct, elles ont besoin de l’une des licences Microsoft 365 répertoriées dans la description du service [Microsoft Teams](/office365/servicedescriptions/teams-service-description). Si vous utilisez déjà Teams, vous disposez probablement de la licence dont vous avez besoin pour organiser et héberger des réunions, des webinaires et des événements en direct.

Pour permettre aux personnes de se connecter à une réunion par téléphone, vous devez configurer l’audioconférence. Pour plus d’informations sur l’audioconférence, consultez [Audioconférence dans Teams](deploy-audio-conferencing-teams-landing-page.md).

## <a name="best-practices-for-large-meetings"></a>Meilleures pratiques pour les grandes réunions

Cette section fournit des conseils aux administrateurs, ainsi que des astuces qu'ils peuvent partager avec leurs présentateurs et organisateurs.

Pour réussir un événement, suivez les pratiques décrites ci-dessous :

- Pour une expérience optimale dans les grandes réunions, Microsoft recommande d’utiliser le client de bureau Teams ou les clients mobiles Teams. 

- Assurez-vous que tous [les principes de connectivité réseau](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles) de Microsoft ont été respectés, tant sur place que pour les utilisateurs distants.
- Utilisez la [télémétrie des données en temps réel](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-real-time-call-quality-analytics/ba-p/2912146) pour surveiller l'événement et identifier tout problème éventuel et sa source.
  - Désignez des moniteurs de réunion pour [analyser](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md) la télémétrie pour les utilisateurs qui font face à une mauvaise expérience causée par des métriques dépassant les seuils.
  - Définissez les moniteurs de réunion comme présentateurs pour désactiver les flux vidéo indésirables, couper les micros en direct accidentels et retirer les participants si nécessaire.

### <a name="guidelines-for-your-end-users"></a>Directives pour vos utilisateurs finaux

Vos organisateurs et présentateurs devraient mettre en œuvre les recommandations ci-dessous :

- Pour créer une réunion fluide, les organisateurs d'événements peuvent définir des présentateurs prédéfinis. Après le début d'une réunion, les présentateurs peuvent également promouvoir d'autres participants au rôle de présentateur.

- Définir un co-organisateur via les options de la réunion (préversion publique)

- Préconfigurez les paramètres de la vidéo et du microphone pour contrôler l'expérience des participants.
  - Désactivez les microphones des participants pour éviter les perturbations. Si quelqu'un a besoin d'interagir pendant la réunion, permettez-lui de couper le son lorsqu'il lève la main.
  - Désactivez la vidéo des participants pour éviter les distractions visuelles. Aux moments appropriés de la réunion, la vidéo peut être autorisée pour tous les participants ou pour des personnes spécifiques.

- Utilisez les sondages et les questions-réponses pendant la réunion.

- Utilisez les commandes du hall d'entrée pour contrôler l'entrée des réunions ou la tenue du hall.

- Exécutez le test de connectivité du réseau [Microsoft 365 pour vérifier l'adéquation du réseau](https://connectivity.office.com/) plusieurs jours avant et le jour de l'événement.

- Si vous présentez depuis votre domicile, vérifiez que d'autres appareils ne consomment pas de bande passante élevée (services de streaming, jeux en ligne, téléchargements volumineux).

- Présentez à partir d'un point d'extrémité avec une connexion câblée pour un partage audio, vidéo et d'écran plus fiable.

- Assurez-vous que les utilisateurs disposent de la dernière application Teams sur un ordinateur de bureau ou un appareil mobile.

- Si vous utilisez un ordinateur portable, vérifiez que la connectivité réseau est élevée et que l'alimentation est suffisante.

- Prévoyez un essai avant l'événement pour identifier les problèmes de dispositifs, d'éclairage ou de réseau. Cela permettra également aux organisateurs/présentateurs de se familiariser avec les fonctions qu'ils utiliseront.
  - Prévoyez des essais supplémentaires si des problèmes ont été rencontrés afin de vous assurer que les efforts de correction ont été couronnés de succès.
  
- Utilisez des fonctionnalités telles que les projecteurs, PowerPoint Live, l'enregistrement des réunions, les sous-titres et les transcriptions pour promouvoir l'engagement et l'efficacité.

- Les présentateurs et les participants doivent utiliser l'application de bureau Teams pour offrir une expérience optimale.

- Les participants devraient désactiver les notifications de chat pendant les grandes réunions pour éviter les distractions.

- Pour plus d’informations sur l’hébergement de grandes réunions, consultez [Meilleures pratiques pour une grande réunion Teams](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16).





## <a name="related-topics"></a>Sujets associés

[Réunions et conférences dans Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md)

[Configurer des webinaires dans Teams](set-up-webinars.md)

[Événements en direct dans Microsoft Teams](teams-live-events/what-are-teams-live-events.md)

[Expérience de réunion en lecture seule de Teams](view-only-meeting-experience.md)

[Spécifications et limites de Microsoft Teams](limits-specifications-teams.md)

[Communauté technique Microsoft : événements en direct dans Microsoft 365](https://resources.techcommunity.microsoft.com/live-events/)
