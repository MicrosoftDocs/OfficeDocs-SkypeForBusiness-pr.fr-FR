---
title: Applications, robots et connecteurs dans Microsoft Teams
ms.reviewer: ''
description: Apprenez-en plus sur les applications, les robots et les connecteurs, ainsi que sur la manière de choisir les éléments à déployer dans Microsoft Teams sur la base du profil de votre organisation et des besoins de votre entreprise.
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 83e5c452cd2e9056818059c5f0b1ddcdeca2c235
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901949"
---
# <a name="apps-bots--connectors-in-microsoft-teams"></a>Applications, robots et connecteurs dans Microsoft Teams

Les applications vous permettent de rechercher du contenu à partir de vos services favoris et de les partager directement dans Teams. Elles vous aident à effectuer des actions telles qu’épingler des services en haut d’un canal, de mener une conversation avec des robots, ou de partager et attribuer des tâches. Pour en savoir plus, voir [Vue d’ensemble sur les applications dans Teams](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).

Nous vous recommandons d’inclure nos applications proposées (par exemple, le Planificateur) dans votre déploiement initial concernant Teams. Ajoutez d’autres applications, robots et connecteurs pour favoriser l’adoption des services Teams.

Vous avez également la possibilité de créer vos propres applications personnalisées. Pour plus d’informations, consultez notre [documentation sur les développeurs](/microsoftteams/platform/overview).

## <a name="apps-deployment-decisions"></a>Décisions liées au déploiement des applications

Teams offre une expérience de collaboration prête à l’utilisation pour votre organisation, et la plupart des organisations trouvent que les paramètres par défaut leur conviennent. Cet article vous permet de décider si vous voulez modifier les paramètres par défaut en fonction du profil de votre organisation et vos exigences professionnelles, puis il vous guide pour chaque modification. Nous avons fractionné les paramètres en deux groupes, en commençant par l’ensemble des [modifications principales que vous êtes le plus susceptible d’apporter](#core-deployment-decisions). Le deuxième groupe inclut les [paramètres supplémentaires](#additional-deployment-decisions) que vous souhaiterez peut-être configurer, en fonction des besoins de votre organisation.

## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Voici les paramètres d’applications que la plupart des organisations veulent modifier (si les paramètres par défaut de Teams ne fonctionnent pas pour l’organisation).

### <a name="app-availability-settings"></a>Paramètres de disponibilité des applications 

Teams fournit un certain nombre d'applications fournies par Microsoft et d'applications tierces pour engager les utilisateurs, soutenir la productivité et intégrer les services d’entreprise couramment utilisés dans Teams. Obtenez les applications à partir du Store Teams. Par défaut, toutes les applications, y compris les applications personnalisées envoyées via le [processus d’approbation du Store Teams](https://docs.microsoft.com/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), sont activées pour tous les utilisateurs. Par exemple, les utilisateurs peuvent utiliser l’application Planificateur pour créer et gérer les tâches d’équipe dans Teams.

Par défaut, toutes les applications fournies par Microsoft et les applications personnalisées sont disponibles et vous pouvez activer ou désactiver les applications individuelles. Il existe un paramètre global au niveau de l’organisation qui vous permet d’activer ou désactiver toutes les applications personnalisées pour toute votre organisation.

| Posez-vous la question | Action |
|--------------|--------|
|Est-ce que vous allez modifier les paramètres par défaut des applications Teams ? | Pour plus d’informations sur les stratégies et les paramètres que vous pouvez utiliser pour gérer les applications de votre organisation, voir [Paramètres d’administration des applications dans Microsoft Teams](admin-settings.md).|
|||

### <a name="app-permissions-and-other-considerations"></a>Autorisations d’applications et autres points à prendre en compte

Les utilisateurs approuvent les applications. Elles sont gérées par l’administrateur ou le spécialiste des TI par l’intermédiaire de stratégies. Toutefois, la plupart du temps, les autorisations et le profil de risque d’une application sont définis dans l’application elle-même. 

| Posez-vous la question | Action |
|--------------|--------|
|<br>Quelles sont les applications auxquelles je souhaite autoriser l’accès ? Quelles sont les applications auxquelles je ne souhaite pas autoriser l’accès ?  | <ul><li>Voir [Autorisations points à prendre en compte pour les applications Microsoft Teams](app-permissions.md) pour obtenir la liste des objets qu’ils faut prendre en compte lorsque vous autorisez l’accès à une application, un robot, un onglet ou le connecteur.</li><li>Voir [Gérer vos applications dans le Centre d'administration Microsoft Teams](manage-apps.md) pour plus d’informations sur la mise à disposition d’une application aux utilisateurs de votre organisation.</li></ul>|
|||

### <a name="bots-for-private-chats-and-channels"></a>Robots pour des conversations et des canaux privés

Les robots sont des programmes automatisés qui répondent aux requêtes ou fournissent des mises à jour et des notifications relatives aux détails que les utilisateurs trouvent intéressants ou veulent suivre. Les robots permettent aux utilisateurs d’interagir avec les services cloud tels que la gestion des tâches, la planification et les sondages dans une conversation Teams. Teams prend en charge les robots dans les canaux et conversations privés. Les administrateurs peuvent contrôler si l’utilisation des robots est autorisée dans une organisation Office 365.

| Posez-vous la question | Action |
|--------------|--------|
|Est-ce que je souhaite autoriser les robots personnalisés dans mon organisation Office 365 ?|Pour plus d’informations sur l’ajout de robots, voir [Ajouter des robots pour conversations et canaux privés dans Microsoft Teams](add-bots.md). Pour plus d’informations sur l’activation ou la désactivation des robots personnalisés, voir [Paramètres d’administration des applications dans Microsoft Teams](admin-settings.md).|
|||

### <a name="built-in-and-custom-tabs"></a>Onglets intégrés et personnalisés

Les propriétaires et membres d'équipe peuvent ajouter d'autres onglets à un canal, une conversation privée ou une conversation de groupe, pour faciliter l'intégration de leurs services cloud. Ajouter des onglets pour améliorer l’accès aux utilisateurs et gérer les données dont ils ont besoin ou qu’ils utilisent le plus souvent. Dans des canaux, les onglets Conversations et Fichiers sont créés par défaut. Dans chaque conversation privée, les onglets Conversations, Fichiers, Organisation et Activité sont créés par défaut. En plus de ces onglets intégrés, vous pouvez créer et ajouter des onglets personnalisés. Pour savoir comment activer ou désactiver les applications Teams pour votre organisation, voir [Paramètres d’administration des applications dans Teams](admin-settings.md).

| Posez-vous la question | Action |
|--------------|--------|
|Est-ce que je souhaite autoriser les onglets personnalisés dans mon organisation Office 365 ?|Pour plus d’informations, voir [Utiliser des onglets intégrés et des onglets personnalisés dans Teams](built-in-custom-tabs.md).|
|||

### <a name="office-365-and-custom-connectors"></a>Connecteurs Office 365 et personnalisés

Avec les connecteurs, votre équipe reste au courant des dernières activités, en leur fournissant directement dans un canal du contenu et des mises à jour de services que vous utilisez fréquemment. Grâce aux connecteurs, vos utilisateurs de Teams peuvent recevoir des mises à jour de services courants tels que Twitter, Trello, Wunderlist, GitHub et les services Azure DevOps dans leurs conversations Teams.

| Posez-vous la question | Action |
|--------------|--------|
|Est-ce que je souhaite permettre aux utilisateurs de créer des connecteurs personnalisés ?|Pour plus d’informations, voir [Utiliser des connecteurs Office 365 et personnalisés dans Teams](office-365-custom-connectors.md).|
|||

## <a name="additional-deployment-decisions"></a>Options de déploiement supplémentaires

Vous souhaiterez peut-être modifier ces paramètres en fonction des besoins et de la configuration de votre organisation.

### <a name="activity-reports"></a>Rapports d’activité

Vous pouvez utiliser les rapports d’activité pour voir comment les utilisateurs de votre organisation utilisent Teams. Par exemple, si certains utilisateurs n’utilisent pas encore Teams, c’est peut-être parce qu’ils ne savent pas comment commencer ou comment utiliser Teams pour être plus productifs et mieux collaborer. Votre organisation peut utiliser les rapports d’activité pour choisir où hiérarchiser les efforts de formation et de communication. Pour afficher les rapports d’activité, vous devez être un administrateur général dans Office 365, un administrateur de service Teams ou un administrateur Skype Entreprise.

| Posez-vous la question | Action |
|--------------|--------|
| <br>Qui a besoin de voir les rapports d’activité et est-ce qu’ils disposent des autorisations appropriées pour les afficher ? |<ul><li>Si vous ne voulez pas attribuer un rôle d’administrateur à un utilisateur, vous pouvez lui [attribuer le rôle de lecteur de rapports](teams-activity-reports.md#reports-reader-role).</li><li>Voir [Rôles et autorisations](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) et [Afficher et attribuer des rôles](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal) pour plus d’informations sur comment attribuer des rôles d’administrateur dans Azure Active Directory.</li></ul> |
|||

### <a name="app-templates"></a>Modèles d’application

Les modèles d’application sont des applications Microsoft Teams prêtes pour la production qui sont impulsées par la communauté, open source et disponibles sur GitHub. Chacune contient des instructions détaillées de déploiement et d’installation pour votre organisation, offrant ainsi une application prête à l’emploi installable et utilisable immédiatement. Le code source complet est également disponible, de sorte que vous pouvez l’explorer en détail ou répliquer le code et le modifier en fonction de vos besoins spécifiques.

| Posez-vous la question | Action |
|--------------|--------|
| Est-ce que je veux installer des modèles d’applications Teams, tels que Icebreaker ? |Pour en savoir plus, lisez [Modèles d’application pour Teams](https://docs.microsoft.com/microsoftteams/platform/samples/app-templates?toc=MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||


## <a name="next-steps"></a>Étapes suivantes
- [Favoriser l’adoption](adopt-microsoft-teams-landing-page.md) d’applications proposées, par exemple, le Planificateur.
- [Mettre en place des réunions et des conférences](deploy-meetings-microsoft-teams-landing-page.md)
- [Mettre en place les services audio dans le nuage](cloud-voice-landing-page.md)


