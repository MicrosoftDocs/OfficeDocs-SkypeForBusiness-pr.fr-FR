---
title: Mise en place de Teams pour les organisations de soins de santé
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
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-overview
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Découvrez les fonctionnalités de soins de santé telles que la téléhealthe de Microsoft Teams, l’intégration EHR, l’intégration du système des travailleurs en ligne et l’application Patients.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: a5b8ea7cddba8def74a1f5b839710cf73bafc67e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125767"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>Mise en place de Teams pour les organisations de soins de santé

Microsoft Teams propose un certain nombre de fonctionnalités de télédédérisme utiles pour les hôpitals et les autres organisations de soins de santé. Des fonctionnalités Teams sont en cours de développement pour aider les hôpitals avec :

- Visites virtuelles et intégration électronique des dossiers médicaux (EHR)
- Packages de stratégie Teams
- Messagerie sécurisée
- Modèles Teams
- Coordination et collaboration pour les soins

Cette fonctionnalité fait partie de Microsoft Cloud pour les soins de santé. Découvrez comment utiliser cette solution qui regroupe les fonctionnalités Azure, Dynamics 365 et Microsoft 365 dans [Microsoft Cloud for Healthcare.](https://docs.microsoft.com/industry/healthcare)

Regardez la vidéo suivante pour en savoir plus sur l’utilisation de la collection de soins de santé pour améliorer la collaboration de l’équipe de santé dans Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> Le contenu de cette section part du principe que vous avez déjà déployé Teams dans votre organisation. Si vous n’avez pas encore déployé Teams, commencez par lire [comment déployer Microsoft Teams.](../../How-to-roll-out-teams.md)

Les scénarios suivants sont disponibles pour les organismes de santé :

| Scénario | Description | Conditions requises |
| -------- | -------- | -------- |
| [Visites virtuelles avec intégration de l’enregistrement médicaux électronique (EHR)](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Planifier, gérer et effectuer des visites virtuelles avec des patients. Ce scénario connecte Microsoft Teams et la plateforme Android pour prendre en charge les visites virtuelles. | Abonnement actif à Microsoft Cloud pour les soins de santé ou abonnement à l’offre autonome Microsoft Teams EHR Connector. <br> Les utilisateurs doivent avoir une licence Microsoft 365 ou Office 365 appropriée qui inclut les réunions Microsoft Teams*. <br> Les organisations doivent avoir cette version en novembre 2018 ou une version ultérieure. <br>[Détails de la exigences de ehr](ehr-admin.md#before-you-begin) |
| [Visites virtuelles avec Microsoft Bookings et l’application Bookings](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | Planifier, gérer et effectuer des visites virtuelles avec des patients. Ce scénario s’appuie sur Microsoft Bookings pour prendre en charge les visites virtuelles. | Microsoft Bookings doit être désactivé pour l’organisation. <br> Tous les utilisateurs de l’application Bookings et tous les membres du personnel participant aux réunions doivent avoir une licence qui prend en charge la planification de réunions Teams*. <br>[Détails de la demande de Bookings](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Packages de stratégie Teams](#teams-policy-packages)| Assurez-vous que les travailleurs cliniques, les travailleurs de l’information et les appareils de salle des patients ont accès aux fonctionnalités de Teams.| Les utilisateurs doivent avoir une licence appropriée*. |
| [Messagerie sécurisée](#secure-messaging) | Attirer plus rapidement l’attention sur les messages urgents et avoir confiance que le message a été reçu et lu. | Les utilisateurs doivent avoir une licence appropriée*.  |
| [Modèles Teams](#teams-templates-for-healthcare-organizations) | Créez des équipes qui incluent un modèle prédéféré de paramètres, de canaux et d’applications préinstallées pour la communication et la collaboration au sein d’un groupe, d’un groupe ou d’un service, ou entre plusieurs distributions, pods et services au sein d’un hôpital. | Les utilisateurs doivent avoir une licence appropriée*.  |
| [Coordination et collaboration pour les soins](#care-coordination-and-collaboration) | Les collaborateurs et le personnel peuvent collaborer en interne sur des plannings, des documents, des tâches, etc.| Les utilisateurs doivent avoir une licence appropriée*. |

*Office 365 A3, A5, E3 et E5, ainsi que Microsoft 365 Business Standard, A3, A5, E3 et E5 sont pris en charge. Pour plus d’informations sur les licences générales de Teams, voir [Gérer l’accès des utilisateurs à Teams.](../../user-access.md)

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>Visites virtuelles et intégration électronique des dossiers médicaux (EHR)

Utilisez la plateforme de réunions complète dans Microsoft Teams pour planifier, gérer et mener des visites virtuelles avec des patients.

- Si votre organisation utilise déjà des dossiers médicaux électroniques (EHR), vous pouvez intégrer Microsoft Teams pour une expérience plus transparente. Microsoft Teams Electronic Health Record (EHR) Connector permet aux uns de lancer facilement la visite d’un patient virtuel ou une consultation avec un autre fournisseur dans Teams directement à partir du système EHR. Pour en savoir plus, voir [Visites virtuelles avec Teams - Intégration à EHR.](ehr-admin.md)
- Si vous n’utilisez pas un ehR pris en charge, vous pouvez utiliser Microsoft Bookings et l’application Bookings dans Teams. Pour en savoir plus, [consultez l’application Bookings et les visites virtuelles dans Microsoft Teams.](../../bookings-app-admin.md)

![Visites virtuelles avec Microsoft Teams](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Packages de stratégie Teams

Appliquez des packages de stratégie Teams pour définir ce que les différents rôles peuvent faire dans Teams. Par exemple, spécifiez les stratégies pour :

- Les travailleurs cliniques, comme les infirmières inscrits, les infirmières et les travailleurs sociaux, afin qu’ils ont un accès total aux discussions, aux appels, à la gestion des shifts et aux réunions.
- Les travailleurs de l’information dans votre organisation de soins de santé, tels que le personnel de l’itatique, le personnel informatique, le personnel financier et les responsables de la mise en conformité, peuvent accéder à un accès total aux discussions, aux appels et aux réunions.
- Salles des patients, pour contrôler les paramètres des appareils des salles des patients.

Pour en savoir plus, consultez [les packages de stratégies Teams pour les soins de santé.](../../policy-packages-healthcare.md)

## <a name="secure-messaging"></a>Messagerie sécurisée

La messagerie sécurisée prend en charge la collaboration au sein des équipes de santé, notamment plusieurs nouvelles fonctionnalités :

- Un expéditeur de message peut définir une priorité spéciale pour son message, de sorte que le destinataire est informé à plusieurs reprises jusqu’à ce qu’il lisent le message.
- L’expéditeur d’un message peut demander une accusé de lecture, de sorte qu’il reçoit une notification lorsqu’un message qu’il a envoyé a été lu par le destinataire du message.

Ensemble, ces fonctionnalités permettent d’attirer plus rapidement l’attention sur les messages urgents et de savoir que le message a été reçu et lu. De nouvelles équipes de santé qui utilisent ces fonctionnalités peuvent être créées pour chaque patient. Ces fonctionnalités sont basées sur une stratégie et peuvent être affectées à des individus ou à l’ensemble de Teams.

Pour en savoir plus, [consultez La mise en place des stratégies de messagerie sécurisée pour les organisations du secteur des soins de santé.](messaging-policies-hc.md)

En relation avec la messagerie sécurisée, la possibilité pour les autres locataires de fédérés par les organisations du secteur des soins de santé d’enrichir la communication entre les locataires. (Voir [Gérer l’accès externe (fédération) dans Microsoft Teams).](../../manage-external-access.md)

## <a name="teams-templates-for-healthcare-organizations"></a>Modèles Teams pour les organisations de soins de santé

De nouveaux modèles de création d’équipes ont été développés pour s’appliquer à un environnement d’hôpital et d’autres seront bientôt créés. Cela facilite la création d’équipes que les travailleurs de la santé utilisent pour coordonner les soins pour les patients de différents services ou services. Pour plus d’informations, voir [Commencer à utiliser les modèles Teams pour les organisations du secteur des soins de santé.](healthcare-templates.md) Teams peut être démarrée pour des services internes tels que des garde, ou pour les soins, et d’autres modèles sont en cours de développement.

## <a name="care-coordination-and-collaboration"></a>Coordination et collaboration pour les soins

Rassemblez votre équipe de santé pour coordonner les soins et collaborer avec Microsoft Teams.

![Soins de santé : Collaborer avec votre équipe de santé dans Teams](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams permet aux enseignants, aux infirmières et aux autres membres du personnel de collaborer efficacement grâce à des fonctionnalités de collaboration incluses dans Microsoft Teams, telles que :

- Configurer des équipes et des canaux pour vos équipes de santé et vos travailleurs de l’information. Utilisez les canaux avec des onglets pour structurer leur travail, avec l’aide supplémentaire des onglets vers lesquels ils peuvent épingler des sources d’informations.
- Discutez, publiez des messages et communiquez. Votre équipe peut avoir des conversations permanentes concernant différents patients qui ont besoin d’attention.
- Appelez les membres de l’équipe de santé et rencontrez-les. Vous pouvez configurer des réunions individuelles ou utiliser les réunions de canal pour gérer les réunions quotidiennes, à la fois à la puissance des fonctionnalités audio, vidéo, de partage d’écran, d’enregistrement et de transcription dans Teams.
- Stockez et partagez des fichiers et des documents. Votre équipe de santé fait partie d’une équipe virtualisée qui travaille et collabore sur des documents Office.

En outre, votre équipe peut utiliser des applications dans Teams pour :

- Partager des listes et suivre des informations avec l’application Listes
- Effectuer le suivi et le suivi des tâches avec l’application Tâches
- Simplifier les approbations avec l’application Approbations
- Créer, gérer et partager des plannings avec l’application Shifts

### <a name="share-lists-and-track-information-with-the-lists-app"></a>Partager des listes et suivre des informations avec l’application Listes

> [!NOTE]
> À compter du 30 octobre 2020, l’application Patients a été retirée et remplacée par l’application [Listes](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) dans Teams. Avec les listes, les équipes de soins de votre organisation de soins de santé peuvent créer des listes de patients pour des scénarios allant des arrondis et des réunions d’équipe de recherche à la surveillance générale des patients.

L’application Listes dans Teams permet aux équipes de suivre les informations et d’organiser le travail. L’application est préinstallée pour tous les utilisateurs de Teams et est disponible sous la direction d’un onglet dans chaque équipe et canal. Les listes peuvent être créées de toutes pièces, à partir de modèles prédéfinés ou en important des données dans Excel.

les équipes de santé peuvent utiliser le modèle Patients pour commencer. Ils peuvent créer des listes pour suivre les besoins et le statut des patients. Les données existantes des patients sur les feuilles de calcul Excel peuvent être rassemblées pour créer une liste dans Teams. Ces listes peuvent être utilisées pour des scénarios tels que les arrondis et le suivi des patients pour coordonner les soins.

Par exemple, une infirmière de charge crée une liste de patients dans une équipe qui inclut tous les membres de l’équipe de santé. Pendant les cycles, l’équipe d’état d’santé accède à Teams sur ses appareils mobiles et met à jour les informations sur les patients dans la liste, que tous les membres de l’équipe peuvent consulter pour rester synchronisé. Lors des sessions d’arrondi où l’équipe d’état d’santé se réunit pour discuter et évaluer les indicateurs clés de performances d’état d’santé pour s’assurer qu’un patient se trouve sur le bon chemin d’accès pour le congé, il peut partager ces informations à l’aide de Teams sur un grand écran d’affichage. membres de l’équipe de santé qui ne sont pas sur le site peuvent la rejoindre à distance.

Voici un exemple de liste qui a été définie pour l’arrondi des patients.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="Capture d’écran d’une liste d’exemples pour l’arrondi des patients":::

Pour en savoir plus, [consultez l’application Gérer les listes pour votre organisation dans Teams.](../../manage-lists-app.md)

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>Effectuer le suivi et le suivi des tâches avec l’application Tâches

Utilisez [Tâches dans](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) Teams pour effectuer le suivi des éléments pour l’ensemble de votre équipe de santé. Votre équipe de santé peut créer, attribuer et planifier des tâches, catégoriser des tâches et mettre à jour l’état à tout moment à partir de n’importe quel appareil exécutant Teams.

Pour en savoir plus, [consultez l’application Gérer les tâches pour votre organisation dans Microsoft Teams](../../manage-tasks-app.md)

### <a name="streamline-approvals-with-the-approvals-app"></a>Simplifier les approbations avec l’application Approbations

Utilisez [les approbations](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) pour simplifier l’ensemble de vos demandes et processus avec votre équipe. Créez, gérez et partagez des approbations directement à partir de votre hub pour le travail d’équipe. Démarrer un flux d’approbation à partir du même endroit que vous envoyez une conversation, dans une conversation de canal ou à partir de l’application Approbations elle-même. Il vous suffit de sélectionner un type d’approbation, d’ajouter des détails, de joindre des fichiers et de choisir les approuveurs. Une fois soumis, les approbations sont informées et peuvent examiner la demande et agir sur cette demande.

Vous pouvez autoriser l’application Approbations pour votre organisation et l’ajouter à vos équipes. Pour en savoir plus sur la gestion des applications, voir [Gérer vos applications dans le Centre d’administration Microsoft Teams.](../../manage-apps.md)

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Créer, gérer et partager des plannings avec l’application Shifts et l’intégration des employés en avant-première

Microsoft Teams est intégré à l’application Shifts et à l’application Frontline Worker, qui peuvent être utilisées pour coordonner les fonctionnalités de shift de personnel, etc. Par exemple, dans Shifts, des infirmières peuvent configurer et coordonner des plannings pour leur personnel, et les infirmières peuvent vérifier les plannings et échanger les shifts. Teams inclut une stratégie de configuration de l’application Employés en avant-première que vous pouvez affecter aux employés en ligne de votre organisation. Par défaut, la stratégie inclut les applications Activité, Shifts, Conversation et Appel. Cette stratégie contrôle le comportement de ces applications, par exemple, en épinglage de l’application Shifts à la barre de l’application pour que l’équipe puisse y accéder rapidement.

Pour en savoir plus, [consultez l’application Gérer shifts pour votre organisation dans Microsoft Teams.](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>Aider vos collaborateurs cliniques et les travailleurs de l’information à prendre en aide Teams

De nombreuses ressources sont disponibles pour aider tous les utilisateurs de votre organisation à se sentir à l’aise avec Teams :

- Visitez le Centre [d’adoption](https://adoption.microsoft.com/microsoft-teams/) de Teams pour obtenir des conseils sur le déploiement de Teams si vous débutez le parcours de votre organisation avec Teams ou développez Teams dans d’autres domaines de votre organisation.
- Envisagez de mettre en place des parcours [d’apprentissage personnalisés](https://adoption.microsoft.com/microsoft-365-learning-pathways/) pour que vos utilisateurs couvrent uniquement les tâches qu’ils doivent effectuer.
- Obtenez de l’aide et une formation pour vos utilisateurs sur la façon d’effectuer des tâches de base dans Microsoft Teams sur le site de [support de Teams,](https://support.microsoft.com/teams)y compris des [vidéos de formation rapide.](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7) Ce site propose également de l’aide [](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)et une formation pour les applications Teams, notamment Listes, [Tâches,](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) [Approbations,](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) [Bookings](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b) [et Shifts.](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
