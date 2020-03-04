---
title: Administrateurs de ressources Microsoft Teams pour l’éducation
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: karsmith
ms.topic: reference
ms.service: msteams
audience: admin
description: Conseils de démarrage de Microsoft teams pour l’éducation à distance.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87d9e36578227c8f27acfdfd07abfa0cadbe69b7
ms.sourcegitcommit: f23c428043bb0b37c9a8600e64691bc2a1f2e874
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/03/2020
ms.locfileid: "42403836"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Prise en main de Microsoft teams pour l’apprentissage à distance

Microsoft teams est une plate-forme qui permet de regrouper les conversations, le contenu, les affectations et les applications en un seul endroit. Créez des salles de classe collaboratives, connectez-vous à des communautés d’apprentissage professionnel et communiquez avec vos collègues, le tout à partir d’une seule et même qualité.

Utilisez les meilleures pratiques décrites dans cet article pour commencer à utiliser Microsoft teams dans le cadre de votre formation. Microsoft teams peut être utilisé pour permettre à la collaboration de classe d’impliquer des étudiants dans des conversations, de fournir une plate-forme de réunion virtuelle et de distribuer des devoirs. Les administrateurs et les membres du personnel enseignant peuvent rester informés et collaborer à l’aide d’équipes relatives aux annonces et aux conversations locales. Les enseignants peuvent partager du contenu didactique à l’aide de la communauté d’apprentissage professionnel.

Microsoft teams dispose de [clients](get-clients.md) disponibles pour le bureau (Windows, Mac et Linux), sur le Web et sur mobile (Android et IOS) pour s’assurer que tous vos employés et étudiants peuvent rester connectés.

En savoir plus sur les scénarios d’utilisation de Microsoft teams dans la [série webinaire teams éducation](https://aka.ms/TeamsEDUWebinars).

## <a name="user-accounts-licenses-and-identity-security"></a>Sécurité des comptes d’utilisateurs, des licences et des identités

Microsoft teams exploite les fonctionnalités de Microsoft 365 pour authentifier les utilisateurs et fournir des services. Les membres du personnel enseignant, les enseignants et les étudiants doivent disposer d’identités établies pour faciliter la collaboration. S’il n’existe pas encore d’identités, suivez ce processus pour les établir.

Pour pouvoir commencer à utiliser les fonctionnalités d’équipe, [les licences d’équipes doivent être activées pour les utilisateurs](user-access.md) . Teams repose sur des fonctionnalités supplémentaires de Microsoft 365 telles que les [groupes Office 365](Office-365-groups.md), [Exchange](Exchange-Teams-interact.md), [SharePoint et OneDrive](SharePoint-OneDrive-interact.md) pour activer les scénarios de collaboration. Les utilisateurs reçoivent la meilleure qualité d’équipe si tous ces services sont également activés. [Teams est pris en charge pour les utilisateurs disposant de messages hébergés par Google](https://docs.microsoft.com/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

## <a name="easily-set-up-microsoft-teams"></a>Configurer facilement Microsoft teams

Pour vous familiariser avec Teams, vous devez procéder comme suit :

### <a name="1-allow-users-to-create-teams"></a>1. permettre aux utilisateurs de créer des équipes

Les étudiants et enseignants peuvent tirer le meilleur parti de teams lorsqu’ils peuvent s’en servir avec des obstacles minimaux et disposer d’une souplesse pour les adapter à leurs besoins. La possibilité pour les utilisateurs d’adapter leurs compétences en équipe consiste à pouvoir créer des équipes qui répondent à leurs besoins. Par **défaut, tout le monde peut créer des groupes et équipes Office 365**. Il peut arriver que cette fonctionnalité ne soit pas appropriée ; par exemple, certains clients peuvent souhaiter limiter les étudiants secondaires à la création d’équipes. Le cas échéant, la création d’un groupe et d’une équipe Office 365 peut être [limitée à certains groupes de sécurité](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups) au sein de votre environnement.

Les clients de niveau supérieur profitent pour permettre à tout le monde, y compris aux étudiants, de créer des équipes de classes, de recherche, de projet de groupe et d’étude. Les écoles primaires peuvent souhaiter limiter la création d’équipes à des étudiants pour s’assurer que tous les étudiants aux communications étudiantes se trouvent au sein d’un forum incluant un adulte. Dans le cas présent, le groupe et la création d’une équipe Office 365 peuvent être limités à tous les enseignants et membres du personnel.

### <a name="2-configure-user-experiences-using-policies"></a>2. configurer des expériences utilisateur à l’aide de stratégies

Les [stratégies d’équipe](teams-policies.md) permettent de contrôler les options disponibles pour des utilisateurs ou des groupes d’utilisateurs spécifiques. Des stratégies peuvent être appliquées pour définir les personnes autorisées à utiliser une conversation privée, des appels privés, une planification de réunions, des types de contenu qui peuvent être partagés, etc.

Des membres du personnel enseignant, des **enseignants et des élèves de plus en plus** avantageux des fonctionnalités intégrées aux politiques par défaut (globales). Certains paramètres de stratégie supplémentaires peuvent être activés pour ajouter d’autres fonctionnalités à Microsoft Teams, notamment [activer les fonctionnalités de traduction dans la stratégie de messagerie](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings) et permettre la transcription automatique de la réunion dans la stratégie de réunion.

**Les étudiants d’école primaire** peuvent nécessiter des fonctionnalités restreintes fournies aux étudiants. Politiques définissez les limites sur ce que les étudiants peuvent faire. Dans la mesure où la population des étudiants est souvent le plus grand nombre d’utilisateurs et qu’ils reçoivent souvent les paramètres les plus restrictifs, il est recommandé de modifier les stratégies d’étudiant en ce qui concerne les stratégies globales (au niveau de l’organisation par défaut).

Voici un ensemble de configurations de stratégie non par défaut courantes qui seraient attribuées aux étudiants principaux, qui pourront limiter les communications sans modérateur entre étudiants :

#### <a name="messaging-policy"></a>Stratégie de messagerie

- Option définie sur « désactivé »
- Giphy de l’évaluation du contenu de l’ensemble sur’strict'
- Traduire les messages définis sur « activé »
- Envoyer des messages urgents en utilisant les notifications de priorité définies sur « désactivé »
- Supprimer les utilisateurs des discussions de groupe définies sur « désactivé »

#### <a name="meeting-policy"></a>Stratégie de réunion

- Autoriser la réunion maintenant dans les canaux définis sur « désactivé »
- Autoriser le complément Outlook à « désactivé »
- Autoriser la planification des réunions de canal définie sur « désactivé »
- Autoriser la planification de réunions privées définies sur « désactivé »
- Autoriser la réunion maintenant dans les réunions privées définies sur « désactivé »

#### <a name="live-events-policy"></a>Politique des événements en direct

- Autoriser la planification définie sur « désactivé »

#### <a name="calling-policy"></a>Stratégie d’Appel

- Rendez les appels privés définis sur « désactivé »

#### <a name="teams-policy"></a>Stratégie teams

- Créer des canaux privés définis sur « désactivé »

Les **membres du personnel de l’école primaire et les enseignants** doivent disposer de politiques qui accordent les fonctionnalités essentielles qui peuvent être limitées aux étudiants. Créez de nouvelles stratégies autorisant la conversation privée et la planification de réunions (paramètres par défaut pour une nouvelle stratégie). [Attribuez ces stratégies à votre personnel enseignant et aux enseignants via l’appartenance au groupe de sécurité](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).

## <a name="start-using-teams"></a>Commencer à utiliser teams

### <a name="create-class-teams-for-secure-classroom-use"></a>Créer des équipes de classe pour Secure Classroom use

Microsoft teams pour l’éducation propose des [types d’équipe spécifiques](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) pour une utilisation éducative. Le [type d’équipe de classe](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) est conçu pour les classeurs dotés de fonctionnalités spécifiques, notamment les affectations, un bloc-notes de cours OneNote, un [dossier de ressources](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988) pour la sécurisation du contenu en lecture seule pour les étudiants, et la possibilité de désactiver le son des étudiants. Il existe deux façons de déployer une équipe de classe :

1. [School Data Sync](https://sds.microsoft.com/) (SDS) peut être **configuré par celui-ci**, ce qui permet de créer des équipes de classe pour toutes les classes basées sur les informations du système d’information scolaire. Ce processus met en service les équipes pour chaque section et permet de synchroniser les listes de votre formateur et de vos étudiants. [Les enseignants pourront préparer leur équipe avant d'](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) admettre les étudiants. Par ailleurs, si un enseignant n’utilise pas l’équipe, les étudiants ne seront pas admis au sein de l’équipe, car celui-ci ne clique jamais sur « Activer ». Le SD prend en charge plus de 80 systèmes d’information scolaire (systèmes SIS) pour l’importation de données, et l' [équipe de support de SDS](https://aka.ms/SDSSupport) est prête à vous aider dans la planification et la configuration.
1. Les **enseignants configurent** leur propre équipe de type de classe et invitez les étudiants. Les enseignants peuvent le faire via [l’ajout d’étudiants à l’équipe, le](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954) [partage d’un code de joint](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)ou [le partage d’un lien vers l’équipe](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). Dans la mesure du possible, il est préférable d’avoir des enseignants pour ajouter leurs étudiants à l’équipe afin de s’assurer que les étudiants ont accès et qu’ils ont été ajoutés à une équipe.

Au terme de la configuration d’une équipe, les propriétaires d’équipe peuvent [personnaliser les paramètres de l’équipe](https://support.office.com/article/find-your-class-team-s-settings-in-microsoft-teams-2592d4de-581d-4952-9028-02317880c158) , y compris l’ajout d’une [image d’équipe](https://support.office.com/article/change-your-team-picture-02ea2af6-b49d-4de8-9551-1a5e472993c0), la [création de canaux](https://support.office.com/article/create-student-project-groups-channels-in-microsoft-teams-f85b3c07-fb87-4b94-883b-9be55f4b1e45?ui=en-US&rs=en-US&ad=US) pour les sujets de cours ou les zones de collaboration de groupe, [l’ajout d’une application](https://support.office.com/article/add-an-app-to-teams-b2217706-f7ed-4e64-8e96-c413afd02f77) telle que Quizlet/Flipgrid/Kahoot pour afficher les contenus éducatifs existants et [mentionner leur équipe pour leur première publication](https://support.office.com/article/using-the-conversation-tab-in-microsoft-teams-53d1c530-3797-4a6f-9892-6760f8763df2) et commencer la conversation.

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>Créer des équipes de membres du personnel enseignant pour la communication et la collaboration du personnel

Les [équipes de type personnel](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) sont conçues pour permettre aux administrateurs scolaires et aux membres du personnel de partager facilement des informations et de collaborer sur des initiatives à l’échelle de l’école, y compris la création d’annonces, la configuration de réunions, le partage de contenu et l’intégration d’applications externes telles que le [planificateur du suivi des tâches](https://support.office.com/article/create-a-plan-with-planner-d000976a-7490-4ddf-b9af-09ee764891e2). Les administrateurs scolaires peuvent ajouter des membres du personnel enseignant à l’équipe via l’Assistant Création d’équipe, [Ajouter des membres après la création de l’équipe](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9), ou [partager un code de joint ou un lien vers l’équipe](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). La [création de canaux](https://support.office.com/article/create-a-channel-in-teams-fda0b75e-5b90-4fb8-8857-7e102b014525) est un excellent moyen d’organiser des conversations et des fichiers par flux de flux ou objet. [Le Guide de mise en route pour les propriétaires d’équipe](https://support.office.com/article/go-to-guide-for-team-owners-75f9669b-bd8f-457d-b60b-ac2ac9c8ead4?ui=en-US&rs=en-US&ad=US) est un excellent point de départ pour en savoir plus sur les fonctionnalités et les fonctions des propriétaires d’équipe.

## <a name="teams-meeting-scenarios"></a>Scénarios de réunion teams

### <a name="collaborative-meetings-for-virtual-classes"></a>Réunions de collaboration pour les classes virtuelles

Les [réunions Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams) prennent en charge jusqu’à 250 participants concurrents, y compris la possibilité de disposer de contenus audio, vidéo, de [partage de contenu](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), de tableaux blancs et de notes partagées. Les réunions peuvent être planifiées dans le client Microsoft teams pour [une réunion au sein d’un espace privé ou au sein d’un canal d’équipe](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams), de sorte que tous les membres de l’équipe en aient connaissance. Les réunions peuvent être enregistrées et enregistrées pour que les participants puissent la revoir ultérieurement. Ces enregistrements peuvent également être [transcrits pour retrouver facilement le contenu](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308) qui a été abordé. Une webcam, un micro et un haut-parleur de téléphone portable peuvent être utilisés pour les réunions, et vous pouvez bénéficier d’une qualité audio et vidéo exceptionnelle grâce aux [périphériques optimisés de Microsoft teams](https://products.office.com/microsoft-teams/across-devices/devices).

### <a name="districtuniversity-events-or-updates"></a>Événements ou mises à jour d’une circonscription/Université

Certaines instructions nécessitent des audiences plus importantes et des capacités de production supplémentaires. Ces réunions ont souvent défini des présentateurs, producteurs et modérateurs Q&A. Microsoft teams prend en charge ces sessions à l’aide d' [événements Microsoft teams Live](teams-live-events/what-are-teams-live-events.md). Les événements en direct peuvent être utilisés dans des scénarios tels que des mises à jour de circonscription ou d’université, des adresses de leadership et des instructions destinées à des classes ou des groupes d’étudiants de grande envergure ou à prolonger votre communauté. En savoir plus sur l’exécution de sessions en direct à l’adresse suivante : [planifier et planifier un événement](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)en direct, [créer un événement en direct](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb), [participer à un événement en direct](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac)et [modérer une&Q](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76).

## <a name="recommended-tips--tricks"></a>Conseils & conseils recommandés

Pour en savoir plus sur l’utilisation de Microsoft teams dans l’éducation, voir [Microsoft teams pour l’éducation](https://support.office.com/article/Teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).

> [!NOTE]
> Certaines fonctionnalités principales de Microsoft Teams ne sont pas propres à l’éducation. Pour obtenir des conseils et astuces pour les principales fonctionnalités d’équipes, voir : [aide et formation sur Microsoft teams](https://support.office.com/teams).

## <a name="adoption-content"></a>Contenu d’adoption

Microsoft a mis en place des recommandations en matière de [contenu d’adoption](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76) et de stratégie pour le déploiement de Microsoft Teams. Le Guide de mise en route de [Microsoft teams](https://teamworktools.azurewebsites.net/tft/index.html) fournit une bonne vue d’ensemble des contenus disponibles et le [Kit de réussite des utilisateurs d’équipes](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip) fournit de nombreux modèles qui peuvent être utilisés pour la sensibilisation aux équipes. Le centre de formation Microsoft fournit des formations spécifiques pour l’éducation concernant l’utilisation de [Microsoft teams](https://education.microsoft.com/learningPath/18793af1) et de [OneNote](https://education.microsoft.com/learningPath/b6e3b5f2) dans la classe.

Les ressources d’adoption supplémentaires sont les suivantes :

- [Vidéos de la barre d’conseils rapide : 90](https://www.youtube.com/playlist?list=PLiluTszfwwMKx-yVe7ekBX6gsLIHf1Z8k)
- [Playlist vidéo de Microsoft teams pour l’éducation](https://www.youtube.com/playlist?list=PLiluTszfwwMKicAo6agloFALEB5WvYNYs)
- [BLOG : Découvrez comment cette école utilise les équipes pour une formation à distance](https://www.wellingtoncollege.cn/tianjin-international/teaching-and-learning-update/)

## <a name="support-readiness"></a>Disponibilité du support technique

Les professionnels de l’informatique et l’équipe du support technique peuvent se familiariser avec l’architecture teams et sous-jacente de l’utilisation des fonctionnalités de Microsoft 365 aux affiches et aux formations techniques de l’administrateur de Microsoft Teams.

Les ressources de support supplémentaires sont les suivantes :

- [Résoudre les problèmes d’installation et de mise à jour de Microsoft teams](troubleshoot-installation.md)
- [Surveillance et gestion de la qualité des appels](monitor-call-quality-qos.md)
- [Vérifier l’intégrité du service pour Microsoft Teams](service-health.md)
- [Ressources de support pour Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Surveillance et gestion de la qualité des appels](monitor-call-quality-qos.md)
- [Vérifier l’intégrité du service pour Microsoft Teams](service-health.md)
- [Ressources de support pour Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Centre d’aide de Microsoft teams](https://support.office.com/en-us/teams)
