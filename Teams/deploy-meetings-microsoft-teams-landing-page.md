---
title: Réunions et conférences dans Microsoft Teams
ms.reviewer: ''
description: Utilisez ces ressources de déploiement pour vous aider à mettre en place des réunions et des conférences audio dans Microsoft Teams.
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
- m365initiative-meetings
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1c41219f080e2270ed27d52688a03891f74ac26d
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605360"
---
# <a name="meetings-and-conferencing-in-microsoft-teams"></a>Réunions et conférences dans Microsoft Teams

> [!NOTE]
> - Pour avoir une vue d’ensemble de la transition vers les ressources pédagogiques et distantes pour vous aider à démarrer, consultez [**la page d’accueil de l’apprentissage à distance**](https://www.microsoft.com/education/remote-learning).
> - Les ressources destinées à aider les enseignants et les étudiants disposant d’une formation à distance sont disponibles dans [**l’enseignement et l’apprentissage à distance dans Microsoft Office 365 pour l’éducation**](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4).


Vous avez terminé la [Prise en main](get-started-with-teams-quick-start.md). Vous avez déployé Teams avec [des conversations, des équipes, des canaux et des applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md) au sein de votre organisation. Vous êtes maintenant prêt à ajouter la charge de travail correspondant aux réunions, y compris les [audioconférences](deploy-audio-conferencing-teams-landing-page.md), les vidéo et le partage. Cet article vous guide dans le déploiement de réunions et de conférences audio. Commencez par regarder notre vidéo sur les réunions, conférences et appareils Teams (3:28 minutes) :

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE46ZdQ]

Pour en savoir plus sur l’expérience des réunions pour vos utilisateurs, consultez[Réunions et appels](https://support.office.com/article/meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8). 


*Nouveautés d’avril 2020* : les organisateurs de réunion peuvent mettre fin à une réunion pour tous les participants à la réunion Teams en cliquant sur **Mettre fin à la réunion** dans les contrôles de réunion au sein de la réunion.  

*Nouveautés en novembre 2019*: vous pouvez désormais [utiliser Advisor pour Teams (préversion) pour vous aider à déployer Microsoft Teams](use-advisor-teams-roll-out.md). Advisor for Teams (préversion) vous guide tout au long du processus de déploiement de Teams, y compris les réunions et conférences. Il évalue votre environnement Office 365 et identifie les configurations les plus courantes que vous devrez peut-être mettre à jour ou modifier avant de pouvoir déployer les réunions et conférences dans Teams.

 > [!Note]
> Pour plus d’informations sur les réunions et conférences Teams sur différentes plateformes, consultez [Fonctionnalités Teams par plateforme](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="meetings-and-conferencing-deployment-decisions"></a>Décisions liées au déploiement de réunions et de conférences

Teams offre une expérience prête à l’utilisation pour votre organisation, et la plupart des organisations trouvent que les paramètres par défaut leur conviennent. Cet article vous permet de décider si vous voulez modifier les paramètres par défaut en fonction du profil de votre organisation et vos exigences professionnelles, puis il vous guide pour chaque modification. Nous avons fractionné les paramètres en deux groupes, en commençant par l’ensemble des [modifications principales que vous êtes le plus susceptible d’apporter](#core-deployment-decisions). Le deuxième groupe inclut les [paramètres supplémentaires](#additional-deployment-decisions) que vous souhaiterez peut-être configurer, en fonction des besoins de votre organisation.

> [!Tip]
> Regardez la session suivante pour en savoir plus sur Meetings : [présentation de Meetings dans Microsoft Teams pour les spécialistes des TI](https://aka.ms/teams-meetings-intro)


## <a name="meetings-and-conferencing-prerequisites"></a>Prérequis pour les réunions et conférences

Avant d'étendre le déploiement de vos réunions à l'ensemble de votre organisation, prenez le temps d'examiner et de confirmer que votre environnement est prêt à offrir aux utilisateurs la meilleure expérience possible. Passer en revue les informations suivantes et apportez les modifications nécessaires à votre environnement selon vos besoins.

Pour tirer le meilleur parti de Teams, votre organisation doit avoir déployé Exchange Online et SharePoint Online, et vous devez avoir un domaine vérifié pour O365 comme *contoso.com*.

Pour étendre les réunions à l'échelle de votre organisation, vous devez vous assurer que tous les sites utilisateurs disposent d'un accès Internet pour se connecter aux services Office 365. Vous devez vous assurer qu’au minimum, les ports courants suivants soient ouverts à internet à partir des emplacements de vos utilisateurs :

- ports TCP 80 et 443 sortants pour les clients qui utiliseront Teams.
- ports UDP 3478 à 3481 sortants pour les clients qui utiliseront Teams.

| Posez-vous la question | Action |
|--------------|--------|
|Mon réseau est-il prêt pour le déploiement de réunions Teams ? | Pour vérifier que votre réseau est prêt, voir :<ul><li>[Préparer le réseau de votre organisation pour Microsoft Teams](./prepare-network.md)</li><li>[URL et plages d’adresses IP](./office-365-urls-ip-address-ranges.md)</li></ul> |
|||

## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Voici les paramètres que la plupart des organisations veulent modifier (si les paramètres par défaut de Teams ne fonctionnent pas pour l’organisation).

### <a name="teams-administrators"></a>Administrateurs Teams

Teams fournit un ensemble de rôles d’administrateur personnalisé qui peuvent servir à gérer des équipes pour votre organisation. Ces rôles fournissent plusieurs fonctionnalités aux administrateurs. 

| Posez-vous la question | Action |
|--------------|--------|
|Qui va assumer le rôle d’Administrateur des Communications Teams ?|Pour en savoir plus sur les rôles d’administrateur Teams, voir [Utiliser les rôles d’administrateur Microsoft Teams pour gérer les équipes](using-admin-roles.md).|
|Qui va assumer le rôle d’ingénieur support des Communications Teams ?|Pour attribuer des rôles d’administrateur, voir [Attribuer des rôles administrateur et non administrateur aux utilisateurs avec Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|Qui va assumer le rôle de spécialiste d’assistance des Communications Teams ?||
|||

### <a name="meetings-settings"></a>Paramètres de réunions 

Les paramètres de réunions sont utilisés pour contrôler si les utilisateurs anonymes peuvent participer à des réunions Teams, configurer des invitations aux réunions et, si vous voulez activer la fonctionnalité de qualité de Service (QoS), configurer les ports pour le trafic en temps réel. Ces paramètres seront utilisés pour toutes les réunions Teams que les utilisateurs prévoient pour votre organisation. 

| Posez-vous la question | Action |
|--------------|--------|
|Est-ce que je vais personnaliser les paramètres de réunion initiaux ? |Voir le [didacticiel Réunions avec Teams](tutorial-meetings-in-teams.yml) pour en savoir plus sur les paramètres de réunions.|
|Est-ce que je vais implémenter la QoS?|Pour plus d’informations sur les concepts de QoS, reportez-vous à la rubrique [Qualité de service dans Microsoft Teams](qos-in-teams.md). scénarios et implémentation.|
|||

### <a name="meeting-policies"></a>Stratégies de réunion

Les stratégies de réunion sont utilisés pour contrôler les fonctionnalités qui sont disponibles aux utilisateurs lorsqu’ils se connectent à des réunions Teams. Vous pouvez utiliser la stratégie par défaut ou créer une ou plusieurs stratégies de réunion personnalisées pour les personnes qui hébergent des réunions dans votre organisation. Pour plus d’informations, voir le [didacticiel Réunions avec Microsoft Team](tutorial-meetings-in-teams.yml).

| Posez-vous la question | Action |
|--------------|--------|
|<ul><li>Est-ce que je vais personnaliser les stratégies de réunion initiales ?</li><li>Est-ce que j’ai besoin de plusieurs stratégies de réunion ?</li><li>Comment déterminer quelles stratégies de réunion sont appliqués à quels groupes d’utilisateurs?</li></ul>|<br>Voir [Gérer les stratégies de réunion dans Teams](meeting-policies-overview.md).|
|||

### <a name="audio-conferencing"></a>Audioconférence

L'audioconférence fournit aux organisations des points d'entrée supplémentaires à toute réunion (ponctuelle ou programmée) en permettant aux participants de s'y joindre via le réseau téléphonique public commuté (RTPC) en utilisant une ligne terrestre traditionnelle, un central téléphonique privé (PBX) ou un téléphone mobile. 

Lorsque vous êtes prêt à mettre en place une conférence Audio, voir le guide approfondi [Déploiement de conférence audio](deploy-audio-conferencing-teams-landing-page.md).

### <a name="meeting-room-and-personal-devices"></a>Salle de réunion et appareils personnels

Pour une expérience optimale de réunion dans Teams, envisagez d’utiliser des appareils pour Teams tels que les systèmes de salle de réunion, téléphones, casques et caméras vidéo. Pour plus d’informations, voir [Appareils pour les communications intelligentes avec Teams](https://products.office.com/microsoft-teams/across-devices).

| Posez-vous la question | Action |
|--------------|--------|
|Est-ce que je vais acheter des appareils personnels pour mes utilisateurs ? |Voir [Gérer vos périphériques dans Microsoft Teams](devices/device-management.md). |
|Est-ce que je vais acheter et déployer des systèmes de salle de conférence pour mes salles de conférence ?|Voir [Solutions et appareils de salle de réunion](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json).|
|||

### <a name="reporting"></a>Rapports

Utilisez les rapports d’activité pour voir la manière dont les utilisateurs de votre organisation utilisent Teams. Par exemple, si certains utilisateurs n’utilisent pas encore Teams, c’est peut-être parce qu’ils ne savent pas comment commencer ou comment utiliser Teams pour être plus productifs et mieux collaborer. Votre organisation peut utiliser les rapports d’activité pour choisir où hiérarchiser les efforts de formation et de communication. 


| Posez-vous la question | Action |
|--------------|--------|
|Qui doit se charger de la création de rapports ?|Voir [Utiliser des rapports d’activité pour Teams](teams-activity-reports.md).  |
|Qui doit se charger de la surveillance de l’utilisation ?|Voir [Surveiller l’utilisation et les commentaires dans Microsoft Teams](get-started-with-teams-monitor-usage-and-feedback.md).|
|||

## <a name="additional-deployment-decisions"></a>Options de déploiement supplémentaires

Vous souhaiterez peut-être modifier ces paramètres en fonction des besoins et de la configuration de votre organisation.

### <a name="bandwidth-planning"></a>Planification de la bande passante

La planification de la bande passante permet aux organisations d’estimer la bande passante requise pour prendre en charge des réunions avec leurs réseaux étendus et les liaisons internet afin de confirmer que le réseau est correctement configuré pour prendre en charge une mise à l’échelle des services de réunion.

> [!IMPORTANT]
> Teams ne permet pas aux utilisateurs de planifier de réunions ou d’événements en direct lorsqu’ils sont hors connexion ou qu’ils utilisent une bande passante limitée.

| Posez-vous la question | Action |
|--------------|--------|
| Est-ce que j’ai besoin de faire une planification concernant la bande passante avant et pendant mon processus de déploiement des réunions ? |Voir [Préparation du réseau](3-envision-evaluate-my-environment.md#network-readiness) pour plus d’informations et voir des liens vers des outils pour simplifier votre processus de planification.|
|||

### <a name="meeting-recording-and-archiving"></a>Enregistrement et archivage des réunions

Les utilisateurs peuvent enregistrer leurs réunions et appels de groupe pour capturer l’audio, la vidéo et le partage des activités à l’écran. Il existe également une option pour les enregistrements qui permet une transcription automatique, afin que les utilisateurs puissent regarder les enregistrements de réunion avec des sous-titres et rechercher des éléments de discussion importants dans la transcription. L’enregistrement se passe dans le nuage et est enregistré avec Microsoft Stream, pour que les utilisateurs puissent le partager en toute sécurité au sein de leur organisation. Pour rechercher l’enregistrement d’une réunion, accédez à la conversation de réunion.

>[!Note]
> Le passage de Microsoft Stream à [OneDrive Entreprise et SharePoint pour les enregistrements de réunion](tmr-meeting-recording-change.md) est une approche à différentes étapes. Au lancement, vous aurez la possibilité de choisir cette expérience. En novembre vous devrez quitter cette option si vous souhaitez poursuivre avec Stream et, au début de 2021 nous exigerons de tous les clients l’utilisation de OneDrive Entreprise et SharePoint pour les nouveaux enregistrements de réunion.

Pour plus d’informations, voir [Enregistrement de réunion Teams dans le nuage](cloud-recording.md).

| Posez-vous la question | Action |
|--------------|--------|
| Est-ce que je vais activer le service de transcription pour la réunion ?|Voir [activer ou désactiver la transcription de l’enregistrement](meetings-policies-recording-and-transcription.md#allow-transcription)|
|||


### <a name="live-events-policies"></a>Stratégies d’événements en direct

Vous pouvez utiliser les stratégies d’événements en direct Teams pour gérer les paramètres d’événement des groupes d’utilisateurs. Vous pouvez utiliser la stratégie par défaut ou créer d’autres stratégies qui peuvent être affectées aux utilisateurs qui gèrent des événements en direct au sein de votre organisation. 

| Posez-vous la question | Action |
|--------------|--------|
| Est-ce que ma société utilise des événements en direct Teams ?| Voir les [articles événements en direct](teams-live-events/what-are-teams-live-events.md) pour plus d’informations sur la planification, la configuration et la configuration d’événements en direct Teams.|
|||

### <a name="conference-room-systems-rollout"></a>Déploiement de systèmes de salle de conférence

Les organisations avec plusieurs salles de conférence peuvent envisager une approche structurée de l’inventaire de leurs salles de conférence, de l’identification des périphériques appropriés, puis de leur déploiement. 



| Posez-vous la question | Action |
|--------------|--------|
| Que dois-je faire pour déployer les systèmes de salle de conférence ?|Consultez les articles [Planifier les Salles Microsoft Teams](/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json).|
|||

### <a name="cloud-video-interop"></a>Interopérabilité de la vidéo dans le nuage

L’interopérabilité de la vidéo dans le nuage permet à des appareils de salle de réunion tiers de participer à des réunions Teams. 

Une téléconférence vidéo avec collaboration de contenu vous permet de tirer le meilleur parti des réunions. Toutefois, cela coûte cher de mettre à niveau les systèmes et appareils de salle de réunion. L’interopérabilité de la vidéo dans le nuage pour Teams fonctionne avec les systèmes tiers et offre une expérience de réunion native à tous les participants – dans les salles de réunion ou dans un client Teams. 

| Posez-vous la question | Action |
|--------------|--------|
| Est-ce que je vais utiliser une solution d’interopérabilité de la vidéo dans le nuage dans le cadre de mon déploiement de systèmes de salle de conférence ? | Voir [Interopérabilité de la vidéo dans le nuage de Microsoft Teams](cloud-video-interop.md).|
|||


### <a name="personal-device-rollout"></a>Déploiement des appareils personnels

Lorsque vous planifiez un déploiement à grande échelle des appareils personnels pour prendre en charge les réunions ou le déploiement des communications audio, envisagez d’utiliser un processus de déploiement site par site renouvelable offrant une qualité répétable.

| Posez-vous la question | Action |
|--------------|--------|
|Est-ce que je vais utiliser une approche site par site de déploiement de réunions ? |  Le [Manuel d’activation de site pour Teams](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads) constitue une bonne base que vous pouvez utiliser pour vos propres déploiements. Le guide se concentre sur la communication audio, mais les principes généraux concernant la remise d’appareil, la disponibilité de compte, l’adoption et la formation s’appliquent à un déploiement pour des réunions à plus grande échelle. |
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>Résoudre les problèmes de qualité de réunion et d’appel 

Teams offre deux façons de surveiller et de résoudre les problèmes de qualité d’appel : [Analytique des appels et Tableau de bord de qualité des appels](monitor-call-quality-qos.md). L’analytique des appels affiche des informations détaillées sur les appareils, les réseaux et la connectivité liés aux appels et réunions spécifiques pour chaque utilisateur. L’analytique des appels est conçue pour aider les administrateurs et agents du support technique à résoudre les problèmes de qualité d’appel concernant des appels spécifiques, alors que le Tableau de bord de qualité des appels est conçu pour aider les administrateurs et les ingénieurs réseau à optimiser un réseau. Le Tableau de bord de qualité des appels se concentre sur des utilisateurs spécifiques et examine plutôt des informations globales pour l'ensemble d'une organisation Teams. 

|Posez-vous la question|Action |
|------------|-------|
| Qui doit se charger de la surveillance et de la résolution des problèmes de qualité d’appel ? | Voir [Utiliser l’Analytique des appels pour résoudre les problèmes de qualité des appels médiocre](use-call-analytics-to-troubleshoot-poor-call-quality.md) pour plus d’informations sur les niveaux d’autorisation requis pour résoudre les problèmes de qualité d’appel.|
|||

### <a name="operate-your-meetings-service"></a>Utiliser votre service de réunions

Il est important de comprendre l’état de santé général du service Teams afin de pouvoir signaler, de manière proactive, aux autres membres de votre organisation, tout événement qui affecte le service. Les articles [Utiliser mon service](1-drive-value-operate-my-service.md) fournissent des instructions détaillées concernant les opérations de service.

|Posez-vous la question|Action |
|------------|-------|
|Qui dans mon organisation doit se charger de la gestion du service de réunions ? | Vérifiez que cette personne dispose des autorisations d’administration Teams dont elle a besoin pour gérer votre service de réunions. Pour en savoir plus sur les rôles d’administrateur Teams, voir [Utiliser les rôles d’administrateur Microsoft Teams pour gérer les équipes](using-admin-roles.md).|
|||


## <a name="next-steps"></a>Étapes suivantes
- [Favoriser l’adoption](adopt-microsoft-teams-landing-page.md) des réunions et conférences au sein de votre organisation.
- [Ajouter une audioconférence](deploy-audio-conferencing-teams-landing-page.md)
- [Mettre en place les services audio dans le nuage](cloud-voice-landing-page.md)
- Inclure des applications proposées (par exemple, le Planificateur) dans votre déploiement initial concernant Teams. Ajoutez d’autres [applications, robots et connecteurs](deploy-apps-microsoft-teams-landing-page.md) pour favoriser l’adoption des services Teams.