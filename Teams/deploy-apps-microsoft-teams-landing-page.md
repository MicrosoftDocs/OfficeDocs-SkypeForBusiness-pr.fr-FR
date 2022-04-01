---
title: En savoir plus sur les applications dans Microsoft Teams
ms.reviewer: ''
description: Découvrez les applications et décidez des applications à autoriser dans Teams en fonction du profil de votre organisation et des exigences métier.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 02/10/2021
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b6fd5ef344550cf85420faef1748c34f6e87e88b
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556525"
---
# <a name="about-apps-in-microsoft-teams"></a>À propos des applications dans Microsoft Teams

Les applications permettent aux utilisateurs de trouver du contenu à partir de leurs services favoris et de les partager dans Teams. Ils vous permettent d’effectuer des tâches telles que épingler des services en haut d’un canal, automatiser les notifications à l’aide de bots ou partager et affecter des tâches. Pour en savoir plus sur l’utilisation des applications, lisez [Vue d’ensemble des applications pour les utilisateurs finaux](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0).

Les différents types d’applications que vos utilisateurs finaux peuvent utiliser dans Teams sont les applications créées par Microsoft, les applications tierces certifiées et les applications personnalisées créées par votre propre organisation.

## <a name="use-microsoft-provided-apps"></a>Utiliser les applications fournies par Microsoft

Teams insère un ensemble d’applications intégrées, notamment Listes, Tâches, Compliments, Approbations, etc. Nous vous recommandons d’inclure les applications proposées Teams (par exemple, le Planificateur) dans votre déploiement initial concernant Teams. Ajoutez d’autres applications au fur et à mesure que vous favorisez l’adoption de Teams. Certaines fonctionnalités par défaut, telles que le flux d’activité, la conversation, le calendrier et les appels, sont disponibles par défaut et épinglées pour faciliter l’accès des utilisateurs finaux.

## <a name="use-third-party-apps"></a>Utiliser des applications tierces

En plus des applications fournies par Microsoft, vous pouvez utiliser des applications tierces validées par Microsoft. Microsoft collabore avec Microsoft 365 partenaires de développement pour fournir les informations nécessaires pour accélérer les décisions relatives à l’utilisation des applications Teams. Pour plus d’informations, consultez [Sécurité et conformité de l’application Microsoft Teams](/microsoft-365-app-certification/teams/teams-apps).

## <a name="use-open-source-sample-apps-provided-by-microsoft"></a>Utiliser des exemples d’applications open source fournis par Microsoft

Vous pouvez utiliser les [Modèles d’application](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json), qui sont des applications Microsoft Teams prêtes pour la production qui sont impulsées par la communauté, open source et disponibles sur GitHub.

## <a name="create-custom-apps"></a>Créer des notifications personnalisées

Vous pouvez créer rapidement des solutions personnalisées à faible code à l’aide de l’intégration de Teams avec [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions). Vous pouvez également créer votre propre application personnalisée en fonction des besoins de votre entreprise. Si vous souhaitez en savoir plus, consultez l’article [Créer des applications Microsoft Teams](/microsoftteams/platform/overview).  

## <a name="apps-deployment-decisions"></a>Décisions liées au déploiement des applications

Teams offre une expérience de collaboration prête à l’utilisation pour votre organisation, et la plupart des organisations trouvent que les paramètres par défaut leur conviennent. Cet article vous permet de décider si vous voulez modifier les paramètres par défaut en fonction du profil de votre organisation et vos exigences professionnelles, puis il vous guide pour chaque modification. Nous avons fractionné les paramètres en deux groupes, en commençant par l’ensemble des [modifications principales que vous êtes le plus susceptible d’apporter](#core-deployment-decisions). Le deuxième groupe inclut les [paramètres supplémentaires](#additional-deployment-decisions) vous pouvez configurer en fonction des besoins de votre organisation.

## <a name="core-deployment-decisions"></a>Décisions liées au déploiement Core

Voici les paramètres d’applications que la plupart des organisations veulent modifier (si les paramètres par défaut de Teams ne fonctionnent pas pour l’organisation).

### <a name="app-availability-settings"></a>Paramètres de disponibilité des applications

Teams fournit plusieurs applications fournies par Microsoft et d'applications tierces pour engager les utilisateurs, soutenir la productivité et intégrer les services d’entreprise couramment utilisés dans Teams.
Obtenez les applications à partir du Store Teams. Par défaut, toutes les applications, y compris les applications personnalisées envoyées via le [processus d’approbation du Store Teams](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), sont activées pour tous les utilisateurs. Par exemple, les utilisateurs peuvent utiliser l’application Planificateur pour créer et gérer les tâches d’équipe dans Teams.

Par défaut, toutes les applications tierces fournies par Microsoft et les applications personnalisées sont disponibles et vous pouvez activer ou désactiver les applications individuelles. Il existe des paramètres au niveau de l’organisation qui vous permettent d’activer ou désactiver toutes les applications tierces et/ou personnalisées pour toute votre organisation.

| Posez-vous la question | Action |
|--------------|--------|
|Est-ce que vous allez modifier les paramètres par défaut des applications Teams ? | Pour plus d’informations sur les stratégies et les paramètres que vous pouvez utiliser pour gérer les applications de votre organisation, voir [Paramètres d’administration des applications dans Microsoft Teams](admin-settings.md).|

### <a name="app-permissions-and-other-considerations"></a>Autorisations d’applications et autres points à prendre en compte

Les utilisateurs approuvent les applications. Elles sont gérées par l’administrateur ou le spécialiste des TI par l’intermédiaire de stratégies. Toutefois, les autorisations d’application et le profil de risque sont définis dans l’application elle-même.

| Posez-vous la question | Action |
|--------------|--------|
|<br>Quelles sont les applications auxquelles je souhaite autoriser l’accès ? Quelles sont les applications auxquelles je ne souhaite pas autoriser l’accès ?  | <ul><li>Voir [Autorisations points à prendre en compte pour les applications Microsoft Teams](app-permissions.md) pour obtenir la liste des objets qu’ils faut prendre en compte lorsque vous autorisez l’accès à une application, un robot, un onglet ou le connecteur.</li><li>Voir [Gérer vos applications dans le Centre d'administration Microsoft Teams](manage-apps.md) pour plus d’informations sur la mise à disposition d’une application aux utilisateurs de votre organisation.</li></ul>|

<!--- TBD: Rewrite this to talk about bots and tabs as a capability of apps. Admins do not govern bots, tabs, etc. Admins only govern apps that contain capabilities such as connectors, bots, etc. This writeup gives an impression that admins manage apps + bots + tabs + connectors, etc.

### Bots for private chats and channels

Bots are automated programs that respond to queries or give updates and notifications about details users find interesting or want to stay informed about. Bots allow users to interact with cloud services such as task management, scheduling, and polling in a Teams chat. Teams supports bots in private chats and channels. Administrators can control whether the use of bots is allowed in a Microsoft 365 or Office 365 organization.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom bots in my organization?|For more information about adding bots, see [Add bots for private chats and channels in Microsoft Teams](/microsoftteams/platform/bots/what-are-bots). For information about turning custom bots on or off, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### Built-in and custom tabs

Owners and team members can add tabs to a channel, private chat, and group chat to help integrate their cloud services. Add tabs to help users access and manage the data they need or use the most. In channels, the Conversations and Files tabs are created by default. In every private chat, the Conversations, Files, Organization, and Activity tabs are created by default. In addition to these built-in tabs, you can design and add custom tabs. To learn about turning Teams apps on or off for your organization, read [Admin settings for apps in Teams](admin-settings.md).

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](built-in-custom-tabs.md).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

## <a name="additional-deployment-decisions"></a>Décisions de déploiement supplémentaires

Vous pouvez modifier ces paramètres en fonction des besoins et de la configuration de votre organisation.

### <a name="activity-reports"></a>Rapports d’activité

Vous pouvez utiliser les rapports d’activité pour voir comment les utilisateurs de votre organisation utilisent Teams. Par exemple, si certains utilisateurs n’utilisent pas encore Teams, c’est peut-être parce qu’ils ne savent pas comment commencer ou comment utiliser Teams pour être plus productifs et mieux collaborer. Votre organisation peut utiliser les rapports d’activité pour choisir où hiérarchiser les efforts de formation et de communication. Pour afficher les rapports d’activité, vous devez être un administrateur général dans Microsoft 365 ou Office 365, un administrateur de service Teams ou un administrateur Skype Entreprise.

| Posez-vous la question | Action |
|--------------|--------|
| <br>Qui a besoin de voir les rapports d’activité et est-ce qu’ils disposent des autorisations appropriées pour les afficher ? |<ul><li>Si vous ne voulez pas attribuer un rôle d’administrateur à un utilisateur, vous pouvez lui [attribuer le rôle de lecteur de rapports](teams-activity-reports.md#reports-reader-role).</li><li>Voir [Rôles et autorisations](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) et [Afficher et attribuer des rôles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) pour plus d’informations sur comment attribuer des rôles d’administrateur dans Azure Active Directory.</li></ul> |

### <a name="app-templates"></a>Modèles d’application

Les modèles d’application sont des applications prêtes pour la production pour Microsoft qui sont basées sur la communauté, open source et disponibles sur GitHub. Chaque application contient des instructions détaillées pour la déployer et l’installer pour votre organisation. Il s’agit d’une application prête à l’emploi que vous pouvez installer et commencer à utiliser immédiatement.

Le code source complet est également disponible, de sorte que vous pouvez l’explorer en détail ou répliquer le code et le modifier en fonction de vos besoins spécifiques.

| Posez-vous la question | Action |
|--------------|--------|
| Est-ce que je veux installer des modèles d’applications Teams, tels que Icebreaker ? |Pour en savoir plus, lisez [Modèles d’application pour Teams](/microsoftteams/platform/samples/app-templates?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=MicrosoftTeams%2ftoc.json).|
