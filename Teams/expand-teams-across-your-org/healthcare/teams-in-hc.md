---
title: Prise en main de Teams pour les organismes de santé
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-overview
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Découvrez les fonctionnalités de soins de santé telles que la télésanté Microsoft Teams, l'intégration du DSE, l'intégration du système de personnel de première ligne et l'application Patients.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 9ca90625fc8b3229d282d9f86ba4e12fdfa56f49
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2022
ms.locfileid: "63050870"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Prise en main de Teams pour les organismes de santé

Microsoft Teams offre un certain nombre de fonctionnalités de télémédecine utiles pour les hôpitaux et autres organismes de santé. Des fonctionnalités Teams sont en cours de développement pour aider les hôpitaux :

- Visites virtuelles et intégration électronique des dossiers médicaux (EHR)
- Packages de stratégies Teams
- Messagerie sécurisée
- Modèles Teams
- Coordination et collaboration avec les soins

Cette fonctionnalité fait partie de Microsoft Cloud pour la santé. Apprenez-en davantage sur l’utilisation de cette solution qui regroupe les fonctionnalités d’Azure, Dynamics 365 et Microsoft 365 sur [Microsoft Cloud pour le secteur de la santé](/industry/healthcare).

Regardez la vidéo suivante pour en savoir plus sur l’utilisation de la collection de soins de santé pour améliorer la collaboration de l’équipe de santé Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> Le contenu de cette section part du principe que vous avez déjà déployé Teams dans votre organisation. Si vous n’avez pas encore déployé Teams, commencez par lire l’article [Comment déployer Microsoft Teams](../../deploy-overview.md).

Les scénarios suivants sont disponibles pour les organismes de santé :

| Scénario | Description | Conditions requises |
| -------- | -------- | -------- |
| [Visites virtuelles avec intégration d’un dossier médicaux électronique (EHR)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Planifier, gérer et mener des rendez-vous virtuels avec des patients. Ce scénario connecte Teams la plateforme Cerner ou Platforme pour prendre en charge les visites virtuelles. | Abonnement actif à Microsoft Cloud pour la santé abonnement à Microsoft Teams’offre autonome de connecteur EHR. <br> Les utilisateurs doivent avoir une licence Microsoft 365 ou Office 365 licence appropriée qui inclut Teams réunions*. <br> Les organisations doivent avoir la version d’édition d’électronique de novembre 2018 ou ultérieure, ou d’une version ultérieure ou de novembre 2018. <br>Détails de la [exigences EHR d’cerner](ehr-admin-cerner.md#before-you-begin) [et d’Qu’est-ce qu’un ehr](ehr-admin.md#before-you-begin) ? |
| [Visites virtuelles avec Microsoft Bookings et l’application Bookings](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Planifier, gérer et mener des rendez-vous virtuels avec des patients. Ce scénario s’appuie sur Microsoft Bookings pour prendre en charge les visites virtuelles. | Microsoft Bookings doit être désactivé pour l’organisation. <br> Tous les utilisateurs de l’application Bookings et tous les membres du personnel participant aux réunions doivent avoir une licence qui prend en charge la planification de réunions Teams*. <br>[Détails sur configuration requise de Bookings](../../bookings-app-admin.md#prerequisites-to-use-the-bookings-app-in-teams)|
| [Packages de stratégie Teams](#teams-policy-packages)| Assurez-vous que les travailleurs cliniques, les travailleurs de l'information et les appareils de la salle des patients disposent d'un accès approprié à la fonctionnalité Teams.| Les utilisateurs doivent avoir une licence appropriée*. |
| [Messagerie sécurisée](#secure-messaging) | Attirez plus rapidement l'attention sur les messages urgents et ayez la certitude que le message a été reçu et lu. | Les utilisateurs doivent avoir une licence appropriée*.  |
| [Modèles Teams](#teams-templates-for-healthcare-organizations) | Créez des équipes qui comprennent un modèle prédéfini de paramètres, de canaux et d'applications préinstallées pour la communication et la collaboration au sein d'un service, d'une unité ou d'un département, ou entre plusieurs services, unités et départements d'un hôpital. | Les utilisateurs doivent avoir une licence appropriée*.  |
| [Coordination et collaboration avec les soins](#care-coordination-and-collaboration) | Les cliniciens et le personnel peuvent collaborer en interne sur les horaires, les documents, les tâches, etc.| Les utilisateurs doivent avoir une licence appropriée*. |

*Office 365 A3, A5, E3, E5, F1, F3, Microsoft 365 A3, A5, E3 et E5, Business Standard sont pris en charge. Si vous souhaitez en savoir plus sur les licences générales de Teams, veuillez consulter la rubrique [Gérer l’accès des utilisateurs à Teams](../../user-access.md).

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Visites virtuelles et intégration électronique des dossiers médicaux (EHR)

Utilisez la plateforme de réunions complètes Teams pour planifier, gérer et mener des rendez-vous virtuels avec des patients.

- Si votre organisation utilise déjà des dossiers médicaux électroniques (EHR), vous pouvez intégrer des Teams pour une expérience plus transparente. Teams connecteur EHR (Electronic Health Record) permet aux cartésiens de lancer facilement une visite de patient virtuel ou une consultation avec un autre fournisseur dans Teams directement à partir du système EHR. Pour plus d’informations, voir Visites virtuelles avec [Teams - Intégration à Cerner EHR](ehr-admin-cerner.md) et Visites virtuelles avec [Teams - Intégration à EhrHhique](ehr-admin.md).
- Si vous n'utilisez pas un DMI pris en charge, vous pouvez utiliser Microsoft Bookings et l'application Bookings dans Teams. Pour en savoir plus, [voir Visites virtuelles avec Teams et l’application Bookings](../bookings-virtual-visits.md).

![Visites virtuelles avec Microsoft Teams.](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Packages de stratégies Teams

Appliquez des packages de stratégie Teams pour définir ce que les différents rôles peuvent faire dans Teams. Par exemple, spécifiez des stratégies pour :

- Les travailleurs cliniques, tels que les infirmières autorisées, les infirmières responsables, les médecins et les travailleurs sociaux, afin qu'ils puissent avoir un accès complet à la conversation, aux appels, à la gestion des équipes et aux réunions.
- Les travailleurs de l’information dans votre organisation de santé, tels que le personnel d’informatique, le personnel administratif, le personnel financier et les responsables de la mise en conformité, peuvent accéder à des conversations, des appels et des réunions.
- Salles des patients, pour contrôler les paramètres des appareils de salle des patients.

Pour en savoir plus, consultez [Packages de stratégie Teams pour la santé publique](../../policy-packages-healthcare.md).

## <a name="secure-messaging"></a>Messagerie sécurisée

La messagerie sécurisée prend en charge la collaboration au sein des équipes de santé, notamment plusieurs nouvelles fonctionnalités :

- L'expéditeur d'un message peut définir une priorité spéciale pour son message, de sorte que le destinataire soit averti à plusieurs reprises jusqu'à ce qu'il lise le message.
- L'expéditeur d'un message peut demander un accusé de lecture, ce qui lui permet d'être informé lorsqu'un message qu'il a envoyé a été lu par son destinataire.

Ensemble, ces fonctionnalités permettent d'accorder une attention plus rapide aux messages urgents et de s'assurer que le message a été reçu et lu. De nouvelles équipes de santé utilisant ces fonctionnalités peuvent être créées sur une base par patient. Ces fonctionnalités sont basées sur des stratégies et peuvent être affectées à des individus ou à des équipes entières.

Pour plus d’informations, consultez [Prise en main des stratégies de messagerie sécurisée pour les organismes de santé](messaging-policies-hc.md).

La possibilité d'avoir d'autres clients fédérés par des organismes de santé, permettant une communication inter-clients plus riche, est également liée à la messagerie sécurisée. (Consultez [Gérer l’accès externe (fédération) dans Microsoft Teams](../../manage-external-access.md)).

## <a name="teams-templates-for-healthcare-organizations"></a>Modèles Teams pour les organismes de santé

De nouveaux modèles de création Teams ont été développés pour s’appliquer à un environnement d’hôpital. D’autres modèles seront bientôt créés. Cela facilite la création d’équipes que les travailleurs du secteur de la santé utilisent pour coordonner les soins des patients de différents services ou traitements. Pour en savoir plus, consultez [Prise en main des modèles Teams pour les organismes de santé](./healthcare-templates-admin-console.md). Teams peut être démarrées pour des services internes tels que le contrôle d’entreprise ou pour les soins. D’autres modèles sont en cours de développement.

## <a name="care-coordination-and-collaboration"></a>Coordination et collaboration avec les soins

Rassemblez votre équipe de santé pour coordonner les soins et collaborer avec Teams.

![Soins de santé : Collaborez avec votre équipe de santé dans Teams.](../../media/teams-healthcare-collaborate-in-teams.png)

Teams aux médecins, aux employés, aux infirmières et aux autres membres du personnel de collaborer efficacement grâce aux fonctionnalités de collaboration incluses dans Teams, telles que :

- Configurer des équipes et des canaux pour vos équipes de santé et les travailleurs de l’information. Utiliser des canaux avec des onglets pour structurer leur travail, avec l’aide des onglets dans lesquels ils peuvent épingler des sources d’informations.
- Discutez, postez des messages et communiquez. Votre équipe peut avoir des conversations permanentes sur les différents patients nécessitant une attention particulière.
- Appelez et rencontrez les membres de l’équipe soignante. Configurez des réunions individuelles ou utilisez les réunions de canal pour gérer les réunions quotidiennes, à la fois grâce aux fonctionnalités audio, vidéo, de partage d’écran, d’enregistrement et de transcription Teams.
- Stockez et partagez des fichiers et des documents. Votre équipe soignante fait partie d’une équipe virtualisée qui travaille et collabore sur des documents Office.

De plus, votre équipe peut utiliser des applications dans Teams pour :

- Partager des listes et suivre des informations avec l’application Listes
- Suivre et surveiller des tâches avec l’application Tâches
- Simplifier les approbations avec l’application Approbations
- Créer, gérer et partager des planifications avec l’application Plannings

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Partager des listes et suivre des informations avec l’application Listes

> [!NOTE]
> À compter du 30 octobre 2020, l’application Patients a été retirée et remplacée par l’[application Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams. Listes permet aux équipes de soins de votre organisation de santé de créer des listes de patients pour différents scénarios (arrondis, réunions d’équipe de formation, surveillance générale des patients, etc.).

L’application Listes dans Teams permet aux équipes de suivre les informations et d’organiser le travail. L’application est préinstallée pour tous les utilisateurs Teams et est disponible sous la direction d’un onglet dans chaque équipe et canal. Listes peut être créée à partir de zéro, à partir de modèles prédéfinis, ou en important des données dans Excel.

Les équipes soignantes peuvent utiliser le modèle Patients pour commencer. Elles peuvent créer des listes pour suivre les besoins et l’état des patients. Les données existantes des patients sur des feuilles de calcul Excel peuvent être apportées pour créer une liste dans Teams. Ces listes peuvent être utilisées pour des scénarios tels que les rondes et la surveillance des patients pour coordonner les soins.

Par exemple, une infirmière responsable crée une liste de patients dans une équipe qui comprend tous les membres de l’équipe soignante. Pendant les rondes, l’équipe soignante accède à Teams sur ses appareils mobiles et met à jour les informations sur les patients dans la liste, que tous les membres de l’équipe peuvent consulter pour rester synchronisés. Lors des rondes, lorsque l’équipe soignante se réunit pour discuter et évaluer les principaux indicateurs de performance en matière de santé afin de s’assurer que le patient pourra bientôt rentrer chez lui, elle peut partager ces informations à l’aide de Teams sur un grand écran.

Voici un exemple de liste qui a été définie pour la ronde des patients.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Capture d’écran d’une liste d’exemples pour l’arrondi des patients.":::

Pour en savoir plus, consultez [Gérer l’application Listes pour votre organisation dans Teams](../../manage-lists-app.md).

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Suivre et surveiller des tâches avec l’application Tâches

Utilisez [Tâches](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) dans Teams pour effectuer le suivi de tâches pour l’ensemble de votre équipe de santé. Votre équipe de santé peut créer, attribuer et planifier des tâches, les catégoriser et mettre à jour leur état à tout moment, depuis n'importe quel appareil utilisant Teams. Les professionnels de l’informatique et les administrateurs peuvent également publier des tâches pour des équipes spécifiques de votre organisation. Par exemple, vous pouvez publier un ensemble de tâches pour de nouveaux protocoles de sécurité ou une nouvelle étape d’admission à utiliser dans un hôpital.

Pour en savoir plus, consultez [Gérer l’application Tasks pour votre organisation dans Microsoft Teams](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Simplifier les approbations avec l’application Approbations

Utilisez [Approbations](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) pour simplifier l’ensemble de vos demandes et processus avec votre équipe. Créez, gérez et partagez des approbations directement à partir de votre hub pour le travail d’équipe. Démarrez un flux d’approbation à partir de l’endroit où vous envoyez une conversation, dans une conversation de canal, ou à partir de l’application Approbations elle-même. Il vous suffit de sélectionner un type d’approbation, d’ajouter des détails, de joindre des fichiers et de choisir les approbations. Une fois envoyés, les approbations sont averties et peuvent examiner la demande et y agir.

Vous pouvez autoriser l’application Approbations pour votre organisation et l’ajouter à vos équipes. Pour en savoir plus, consultez [Disponibilité de l’application Approbations Teams](../../approval-admin.md).

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Créer, gérer et partager des planifications avec l’application Plannings et intégration de travailleur de première ligne

Teams est intégré à l’application Plannings et à l’application Employé de première ligne, qui peuvent être utilisées pour coordonner les fonctionnalités de personnel en équipe, etc. Par exemple, dans Plannings, les gestionnaires d'infirmières peuvent établir et coordonner les horaires de leur personnel, et les infirmières peuvent vérifier les horaires et changer d'équipe. Teams inclut une stratégie de configuration d’application FrontlineWorker intégrée que vous pouvez affecter aux employés de terrain dans votre organisation. Par défaut, la stratégie inclut les applications Activité, Plannings, Conversation et Appel. Cette stratégie contrôle le comportement de ces applications, par exemple, en épinglage de l’application Plannings à la barre d’application pour que l’équipe puisse y accéder rapidement.

Pour en savoir plus, consultez [Gérer l’application Plannings pour votre organisation dans Microsoft Teams](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md).

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Aidez vos collaborateurs cliniques et information à prendre en pratique Teams

De nombreuses ressources sont disponibles pour aider tous les utilisateurs de votre organisation à se familiariser avec l'utilisation de Teams :

- Visitez le [Centre d'adoption de Teams](https://adoption.microsoft.com/microsoft-teams/) pour obtenir des conseils sur le déploiement de Teams si votre organisation vient de commencer son parcours avec Teams, ou sur l'extension de Teams à d'autres secteurs de votre organisation.
- Envisagez de créer des [parcours d’apprentissage](https://adoption.microsoft.com/microsoft-365-learning-pathways/) personnalisées pour à vos utilisateurs afin qu’ils couvrent uniquement les tâches qu’ils doivent effectuer.
- Obtenez de l’aide et une formation pour vos utilisateurs sur la façon d’effectuer des tâches de base dans Teams sur le [site de support Teams,](https://support.microsoft.com/teams) y compris des [vidéos de formation rapide](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7). Ce site propose également des formations et des aides pour les applications Teams, notamment [Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db), [Tâches](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070), [Approbations](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3), [Bookings](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b)et [Plannings](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821).
