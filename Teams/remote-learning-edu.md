---
title: Ressources Microsoft Teams pour les administrateurs dans l’éducation
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: karsmith
ms.topic: reference
ms.service: msteams
audience: admin
description: Conseils pour le démarrage de l'apprentissage à distance pour Microsoft Teams pour l’Éducation.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2455a725822183d3e953993632a634a43002523
ms.sourcegitcommit: 0286eec17b7eea486b857a69fb6c6166ef0799d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/04/2020
ms.locfileid: "42408879"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Prise en main de Microsoft Teams pour l'apprentissage à distance

Microsoft Teams est une plateforme qui centralise les conversations, le contenu et les applications au même endroit. Créez des salles de classe collaboratives, connectez-vous à des communautés d’apprentissage professionnels et communiquez avec vos collègues et ce, à partir d'une seule expérience.

Utilisez les pratiques conseillées dans cet article pour commencer à utiliser Microsoft Teams pour vos besoins pédagogiques afin d’activer les fonctionnalités d’apprentissage à distance. Microsoft Teams permet d’activer la collaboration en classe en impliquant les étudiants dans des conversations, en offrant une plateforme de réunion virtuelle et en distribuant les devoirs. Les administrateurs et les membres du personnel scolaire peuvent se tenir à jour et collaborer à l’aide de Teams pour les messages d'information et les conversations courantes. Les enseignants peuvent partager du contenu didactique en utilisant les Communautés de formation professionnelle.

Microsoft Teams a des [clients](get-clients.md) disponibles pour les ordinateurs de bureau (Windows, Mac et Linux), web et mobiles (Android et iOS) pour s’assurer que tous les membres du personnel et les étudiants puissent rester connectés.

Pour en savoir plus sur les scénarios d’utilisation de Microsoft Teams, consultez la [série de webinaires Teams pour l’éducation](https://aka.ms/TeamsEDUWebinars).

## <a name="user-accounts-licenses-and-identity-security"></a>Les comptes d'utilisateur, les licences et la sécurité des identités

Microsoft Teams tire parti des fonctionnalités de Microsoft 365 pour authentifier les utilisateurs et offrir des services. Le personnel, les enseignants et les étudiants doivent avoir des identités établies pour faciliter la collaboration. Si les identités n’existent pas encore, suivez ce processus pour les créer.

[Les licences Teams doivent être activées pour les utilisateurs](user-access.md) pour qu'ils puissent commencer à utiliser les fonctionnalités Teams. Teams s’appuie sur des fonctionnalités supplémentaires de Microsoft 365 telles que les [groupes Office 365](Office-365-groups.md), [Exchange](Exchange-Teams-interact.md), [SharePoint et OneDrive](SharePoint-OneDrive-interact.md) pour autoriser les scénarios de collaboration. Les utilisateurs bénéficient d’une expérience Teams optimale si tous ces services sont également activés. [Teams est pris en charge pour les utilisateurs disposant d’une adresse de messagerie hébergée chez Google](https://docs.microsoft.com/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

## <a name="easily-set-up-microsoft-teams"></a>Configurer sans peine Microsoft Teams

Deux actions sont à effectuer pour que vous deveniez opérationnel avec Teams :

### <a name="1-allow-users-to-create-teams"></a>1. Autoriser les utilisateurs à créer des équipes

Les étudiants et les enseignants tirent le meilleur parti de Teams lorsqu’ils peuvent l'utiliser avec le minimum d'obstacles et avoir la souplesse nécessaire pour l'adapter à leurs besoins. L’une des façons dont les utilisateurs peuvent personnaliser leur expérience Teams est d'avoir la possibilité de créer des équipes qui répondent à leurs besoins. **Par défaut, tout utilisateur peut créer des groupes Office 365 et Teams**. Cette fonctionnalité peut être inadéquate, par exemple, certains clients peuvent souhaiter limiter la création Teams par des étudiants de l'enseignement primaire/secondaire. Au besoin, la création de groupe Office 365 et Teams peut être [limitée à certains groupes de sécurité](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups) dans votre environnement.

Les clients de l’enseignement supérieur sont favorisés lorsque tout le monde, y compris les étudiants, peut créer des équipes pour des cours, des recherches, des projets de groupe et des groupes d’étude. Les établissements d’enseignement primaire et secondaire peuvent limiter la création Teams par les étudiants pour s’assurer que toutes les communications entre étudiants se déroulent trouvent dans un forum comprenant un adulte. Dans ce cas, la création de groupe Office 365 et Teams peut être limitée à tous les enseignants et membres du personnel.

### <a name="2-configure-user-experiences-using-policies"></a>2. Configurer des expériences utilisateur à l’aide de stratégies

[Les stratégies Teams](teams-policies.md) offrent la possibilité de contrôler les options disponibles pour des utilisateurs ou groupes d’utilisateurs précis. Les stratégies peuvent être appliquées pour définir qui peut être autorisé à utiliser la conversation privée, l’appel privé, la planification de réunions, les types de contenus pouvant être partagés, etc.

**Les étudiants, éducateurs et enseignants de l'enseignement supérieur** bénéficient des fonctionnalités incluses dans les stratégies par défaut (générales). Certains paramètres de stratégie supplémentaires peuvent être activés pour ajouter des fonctionnalités à Microsoft Teams, notamment [permettre l'activation des fonctionnalités de traduction dans la stratégie de messagerie](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings) et d’autoriser la transcription automatique des réunions dans la stratégie de réunion.

Des fonctionnalités restreintes peuvent être nécessaires pour les **étudiants de l’enseignement primaire et secondaire**. Les stratégies définissent des limites relatives à ce que les étudiants peuvent faire. La population étudiante représentant souvent le plus grand nombre d’utilisateurs qui bénéficie fréquemment des paramètres les plus restrictifs, il est conseillé d’apporter des modifications de stratégies étudiant de façon « Général » (à l’échelle de l’organisation par défaut).

Voici un série courante de configurations de stratégie non définies par défaut qui seraient attribuées aux étudiants de primaire et secondaire pour limiter les communications libres entre étudiants :

#### <a name="messaging-policy"></a>Stratégie de messagerie

- Définir l'ensemble sur « désactivé »
- L’évaluation du contenu Giphy est définie sur « strict »
- Traduire les messages est configuré sur « activé »
- Envoyer des messages urgents à l’aide de notifications de priorité défini sur « désactivé »
- Supprimer les utilisateurs dans des conversations du groupe définies sur « désactivé »

#### <a name="meeting-policy"></a>Stratégie de réunion

- Autoriser Conférence maintenant dans les canaux configuré sur « désactivé »
- Autoriser le complément Outlook défini sur « désactivé »
- Autoriser la planification de réunions configurée sur « désactivé »
- Autoriser la planification de réunions privées définie sur « désactivé »
- Autoriser Réunion maintenant configuré sur « désactivé »

#### <a name="live-events-policy"></a>Stratégie d’événements en direct

- Autoriser la planification définie sur « désactivé »

#### <a name="calling-policy"></a>Stratégie d’Appel

- Définir les appels privés sur « désactivé »

#### <a name="teams-policy"></a>Stratégie Teams

- Créer des canaux privés configuré sur « désactivé »

**Les employés et enseignants d'école primaire** doivent se voir affecter des stratégies autorisant des fonctionnalités de base pouvant être limitées pour les étudiants. Créez des stratégies qui autorisent la conversation privée et la planification de réunions (paramètres par défaut pour une nouvelle stratégie). [Attribuez ces stratégies à votre personnel enseignant et à vos enseignants par le biais de l'adhésion à un groupe de sécurité](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).

## <a name="start-using-teams"></a>Utilisation de Teams

### <a name="create-class-teams-for-secure-classroom-use"></a>Créez des équipes de cours pour une utilisation sûre de la classe

Microsoft Teams pour l’éducation offre des [types d’équipe spécifiques](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) pour l’utilisation scolaire. Le [type d’équipe de classe](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) est conçu pour les salles de cours qui incluent des fonctionnalités spécifiques, notamment les devoirs, un bloc-notes OneNote pour la classe, un [dossier de cours](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988) pour la sécurisation du contenu en lecture seule pour les étudiants, et la possibilité de désactiver le son des étudiants perturbateurs. Les équipes de classe peuvent être déployées de plusieurs manières :

1. [School Data Sync](https://sds.microsoft.com/) (SDS) peut être **configuré par le service informatique**, pour pouvoir créer des équipes de cours pour toutes les classes basées sur les informations du système d’information de l'école. Ce processus mettra en place des équipes pour chaque section et assurera la synchronisation de vos listes d’enseignants et d’étudiants. Les [éducateurs auront la possibilité de préparer leur équipe](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) avant d’admettre des étudiants. Par ailleurs, si un enseignant n’utilise pas l’équipe, les étudiants ne sont pas admis dans l’équipe, car l’enseignant ne clique pas sur « Activer ». School Data Sync (SDS) prend en charge plus de 80 Systèmes d’information scolaire (SIS) pour l’importation de données, et l’[équipe de support SDS](https://aka.ms/SDSSupport) est prête à vous aider pour la planification et la configuration.
1. Les **enseignants configurent** leur propre équipe de type de classe et invitent des étudiants. Les enseignants peuvent effectuer cette opération via l'[ajout des étudiants dans l'équipe](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954), le [partage d'un code de participation](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)ou le [partage d'un lien avec l'équipe](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). Dans la mesure du possible, il est préférable que les enseignants ajoutent leurs étudiants à l’équipe pour garantir l'accès des étudiants et leur notification d'ajout à l’équipe.

Une fois que vous avez configuré l’équipe, les propriétaires d’équipe peuvent personnaliser les paramètres de leur équipe y compris l’ajout d’une image d'équipe, créer des canaux pour des sujets de cours ou des zones de collaboration de groupe, ajouter une application telle que Quizlet/Flipgrid/Kahoot pour faire émerger le contenu éducatif existant, et [mentionner leur équipe dans leur première publication](https://support.office.com/article/using-the-conversation-tab-in-microsoft-teams-53d1c530-3797-4a6f-9892-6760f8763df2) pour informer tout le monde et commencer la conversation.

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>Créez des équipes pour la communication et la collaboration du personnel

Les [équipes de type personnel](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) sont créées pour permettre aux administrateurs scolaires et aux membres du personnel enseignant de partager aisément des informations et de travailler ensemble sur des initiatives à l’échelle de l’école, notamment de créer des annonces, mettre en place des réunions, partager du contenu et intégrer des applications externes, telles que des [planificateurs pour le suivi des tâches](https://support.office.com/article/create-a-plan-with-planner-d000976a-7490-4ddf-b9af-09ee764891e2). Les administrateurs scolaires peuvent ajouter des membres du personnel de l'école à l’équipe via l’Assistant de création d’équipe, [en ajoutant des membres une fois l’équipe créée](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9), ou en [partageant un code de participation ou un lien vers l'équipe](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). La [création de canaux](https://support.office.com/article/create-a-channel-in-teams-fda0b75e-5b90-4fb8-8857-7e102b014525) est un excellent moyen d’organiser des conversations et des fichiers par flux de travail ou sujet. Le [Guide d'accès pour les propriétaires d’équipe](https://support.office.com/article/go-to-guide-for-team-owners-75f9669b-bd8f-457d-b60b-ac2ac9c8ead4?ui=en-US&rs=en-US&ad=US) est un excellent point de départ pour en savoir plus sur les fonctionnalités et les fonctions des propriétaires d’équipe.

## <a name="teams-meeting-scenarios"></a>Scénarios de réunions Teams

### <a name="collaborative-meetings-for-virtual-classes"></a>Réunions collaboratives pour les classes virtuelles

Les [réunions Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams) prennent en charge jusqu’à 250 participants simultanés, y compris la possibilité d’avoir du son, une vidéo, un [partage de contenu](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), des tableaux blancs et des notes partagées. Les réunions peuvent être planifiées au sein du client Microsoft Teams pour une [réunion au sein d’un espace privé ou au sein d’un canal d’équipe](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams), pour que tous les membres de l’équipe en prennent connaissance. Les réunions peuvent être enregistrées et sauvegardées pour être consultées par la suite. Ces enregistrements peuvent également être [transcrits afin de rechercher facilement dans le contenu](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308) abordé. Vous pouvez utiliser un ordinateur portable ou un téléphone mobile avec webcam, un microphone et un haut-parleur pour les réunions. Vous pouvez optimiser la qualité audio/vidéo à l'aide des [appareils Microsoft Teams optimisés](https://products.office.com/microsoft-teams/across-devices/devices).

### <a name="districtuniversity-events-or-updates"></a>Événements ou mises à jour de départements/d'universités

Certains enseignements nécessitent des audiences plus grandes et des fonctionnalités de production supplémentaires. Ces réunions ont souvent défini des présentateurs, des producteurs et des animateur de Q&R. Microsoft Teams prend en charge ces sessions à l’aide des [événements en ligne Microsoft Teams](teams-live-events/what-are-teams-live-events.md). Les événements en temps réel peuvent être utilisés dans le cadre de scénarios, tels que des mises à jour à l’échelle du département ou de l’université, des adresses de direction et pour des enseignements destinés à des catégories ou groupes d’étudiants importants, ou pour les étendre à votre communauté. En savoir plus sur l'organisation de sessions en direct sur : [concevoir et planifier un événement en direct](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502), [créer un évènement en direct](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb), [assister à un événement en direct](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac) et [animer une séance de Q&R](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76).

## <a name="recommended-tips--tricks"></a>Conseils & astuces recommandés

Pour en savoir plus sur l’utilisation de Microsoft Teams dans le secteur de l’Éducation, consultez la page [Microsoft Teams pour l'Éducation](https://support.office.com/article/Teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).

> [!NOTE]
> Certaines fonctionnalités clés de Microsoft Teams ne sont pas particulières à l’éducation. Vous trouverez des conseils et des astuces pour les principales fonctionnalités Teams sur : [Apprentissage et aide sur Microsoft Teams](https://support.office.com/teams).

## <a name="adoption-content"></a>Contenu d'adoption

Microsoft a développé l'[adoption de contenu](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76) et des conseils de stratégie pour déployer Microsoft Teams. Le Guide d’adoption de Microsoft Teams offre une vue d’ensemble du contenu disponible et le [Kit de réussite du client Teams](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip) fournit de nombreux modèles qui peuvent être utilisés pour la prise en compte de Teams. Le Centre des instructeurs Microsoft offre une formation spécifique au monde éducatif sur la façon dont [Microsoft Teams](https://education.microsoft.com/learningPath/18793af1) et [OneNote](https://education.microsoft.com/learningPath/b6e3b5f2) sont utilisés dans la classe.

Les ressources d’adoption supplémentaires sont les suivantes :

- [Courtes vidéos de conseils « Champ des possibilités en 90 secondes ! »](https://www.youtube.com/playlist?list=PLiluTszfwwMKx-yVe7ekBX6gsLIHf1Z8k)
- [Playlist de vidéos sur Microsoft Teams pour l’Éducation](https://www.youtube.com/playlist?list=PLiluTszfwwMKicAo6agloFALEB5WvYNYs)
- [BLOGUE : découvrez comment cette école utilise Teams pour l’enseignement à distance](https://www.wellingtoncollege.cn/tianjin-international/teaching-and-learning-update/)

## <a name="support-readiness"></a>Préparation pour la prise en charge

Les professionnels de l’informatique et les membres du support technique peuvent se familiariser avec l’architecture Teams et l’utilisation sous-jacente des fonctionnalités de Microsoft 365 à l'aide d'affiches et d'une formation technique d'administration sur l’architecture informatique de Microsoft Teams.

Les ressources supplémentaires de support sont les suivantes :

- [Résoudre les problèmes d’installation et de mise à jour Microsoft Teams](troubleshoot-installation.md)
- [Surveillance et gestion de la qualité des appels](monitor-call-quality-qos.md)
- [Vérifier l’intégrité du service pour Microsoft Teams](service-health.md)
- [Ressources de support pour Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Surveillance et gestion de la qualité des appels](monitor-call-quality-qos.md)
- [Vérifier l’intégrité du service pour Microsoft Teams](service-health.md)
- [Ressources de support pour Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Centre d'aide de Microsoft Teams](https://support.office.com/fr-FR/teams)
