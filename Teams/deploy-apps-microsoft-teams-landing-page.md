---
title: En savoir plus sur les applications dans Microsoft Teams
ms.reviewer: ''
description: Découvrez les applications et décidez des applications à autoriser dans Teams en fonction du profil de votre organisation et des exigences métier.
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
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
ms.openlocfilehash: f8579d7c2c49749058c174aa71430803dce63286
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2022
ms.locfileid: "64643018"
---
# <a name="about-apps-in-microsoft-teams"></a>À propos des applications dans Microsoft Teams

Les applications permettent de réunir les outils et services de votre lieu de travail et de collaborer avec d’autres personnes. Les applications aident les utilisateurs finaux à être plus productifs, collaboratifs et efficaces dans leurs tâches quotidiennes. Les organisations utilisent des applications pour communiquer avec leurs clients, fournir des services et partager des informations. Les applications permettent aux utilisateurs d’être plus efficaces dans Teams conversations, réunions et canaux. Par exemple, les utilisateurs finaux utilisent un calendrier épinglé dans Teams pour collaborer rapidement avec d’autres personnes, une application avec la fonctionnalité des bots informant les utilisateurs de la QoS d’un service web dans un canal Teams et une application pour partager et attribuer des tâches à différents utilisateurs finaux dans un canal.

Notre sélection étendue d’applications validées et sécurisées dans le Store permet aux utilisateurs finaux d’accéder aux outils et services dont votre organisation a besoin au quotidien. Microsoft Teams applications SaaS basées sur le web qui n’ont pas besoin d’être déployées. Les utilisateurs finaux peuvent utiliser des applications dans Teams uniquement en fonction des autorisations que vous avez fournies. En tant qu’administrateur, vous approuvez ou bloquez l’utilisation d’une application pour les utilisateurs de votre organisation. Vous contrôlez la disponibilité des applications pour tous les utilisateurs au sein des réunions, conversations et canaux.

Pour fournir à vos utilisateurs finaux les applications dont ils ont besoin, lisez la suite pour comprendre les types d’applications et l’endroit où vos utilisateurs accèdent à ces applications. Pour en savoir plus sur l’utilisation des applications, voir [Vue d’ensemble des applications pour les utilisateurs finaux](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

Les différents types d’applications que vos utilisateurs finaux peuvent utiliser dans Teams sont les Teams disponibles :

* [Les principales applications qui font partie de Teams](#core-apps).
* Autres [applications créées par Microsoft](#microsoft-provided-apps).
* [Applications tierces par](#third-party-apps-validated-by-microsoft) partenaires (validées par Microsoft).
* [Applications personnalisées](#custom-apps) créées par votre propre organisation.

## <a name="core-apps"></a>Applications principales

Certaines fonctionnalités par défaut telles que le flux d’activités, les Teams, les discussions, le calendrier et les appels sont disponibles et épinglées par défaut pour des facilités d’accès pour les utilisateurs finaux. En tant qu’administrateur, vous pouvez modifier le comportement par défaut à l’aide [d’une stratégie d’installation](/microsoftteams/teams-app-setup-policies).

:::image type="content" source="media/core-apps-pinned1.png" alt-text="Les applications principales sont épinglées dans Teams par défaut." lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Applications fournies par Microsoft

Microsoft fournit de nombreuses applications pour améliorer la productivité et la collaboration. Vous et les utilisateurs finaux pouvez trouver ces applications en cherchant Microsoft répertorié comme Publisher dans le Centre d’administration ou en tant que Fournisseur dans le Magasin d’équipes.

Teams insère un ensemble d’applications intégrées, notamment Listes, Tâches, Compliments, Approbations, etc. Nous vous recommandons d’inclure les applications proposées Teams (par exemple, le Planificateur) dans votre déploiement initial concernant Teams.

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Applications Microsoft dans le Centre Teams’administration Microsoft" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>Applications tierces validées par Microsoft

En plus des applications fournies par Microsoft, vous pouvez utiliser des applications tierces validées par Microsoft. Microsoft valide les fonctionnalités et la sécurité de ces applications avant de les rendre disponibles dans Teams Store.

<!--- TBD: Link to the new article later when it is created.
To understand the benefits of app validation, see [validation of third-party apps]().

--->

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Exemple d’applications tierces dans Teams Store":::

<!--- TBD: Check the relevance of this link here.
For more information, see [Microsoft Teams App Security and Compliance](/microsoft-365-app-certification/teams/teams-apps).
--->

## <a name="custom-apps"></a>Applications personnalisées

Les applications créées par les développeurs de votre organisation sont appelées applications personnalisées. Le développement d’une telle application est demandé pour des exigences spécifiques de votre organisation et vous avez des contrôles pour autoriser ou non ces applications. Les développeurs de votre organisation peuvent rapidement créer des solutions personnalisées à faible code en utilisant Teams’intégration à [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Une fois qu’un administrateur a permis l’utilisation d’applications personnalisées, les utilisateurs  finaux trouvent ces applications en cliquant sur Conçu pour votre organisation dans le navigation gauche du Teams store.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Applications personnalisées du Teams store dans Teams de bureau" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>Comprendre le chargement d’applications personnalisées

Lors du développement d’applications personnalisées et avant de les distribuer aux utilisateurs finaux, les développeurs testent les applications en les ajoutant au Store pour les tester elles-mêmes ou avec une équipe dans laquelle ils testent l’application. Cette méthode, appelée chargement sideloading d’applications, s’applique uniquement aux applications personnalisées.

Les développeurs peuvent recharger une application pour la mettre à la disposition des membres d’une équipe spécifique, généralement pour tester une application en cours de développement. Cela ne nécessite pas d’approbation de l’administrateur si le chargement d’un sideloading est autorisé. En tant qu’administrateur, vous pouvez ne pas utiliser le chargement sideloading pour n’importe quel développeur.

Si vous ne souhaitez pas télécharger une version test, les développeurs peuvent encore tester leurs applications dans un [client test](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Une fois le développement d’application personnalisée terminé, les développeurs demandent aux administrateurs de distribuer leur application personnalisée aux utilisateurs finaux. Pour plus d’informations, [voir comment publier une application personnalisée](/microsoftteams/upload-custom-apps). En tant qu’administrateur, vous pouvez autoriser ou non l’utilisation d’une application personnalisée pour des utilisateurs spécifiques.

### <a name="about-app-templates"></a>À propos des modèles d’application

Les modèles d’application pour Teams sont des exemples d’applications fonctionnels prêts pour la production créés par Microsoft pour illustrer les cas d’utilisation les plus utilisés, présenter les meilleures pratiques en matière de développement d’applications et fournir des applications open source que les développeurs peuvent développer pour créer des applications personnalisées. Les développeurs de votre organisation personnalisent les modèles d’application pour les besoins de votre organisation grâce aux modifications simples apportées au code disponible dans GitHub. En tant qu’administrateur, vous fournissez ces applications comme applications personnalisées pour vos utilisateurs finaux.

Pour plus d’informations, [voir Microsoft Teams modèles d’application](https://adoption.microsoft.com/microsoft-teams/app-templates/).

## <a name="understand-app-capabilities"></a>Comprendre les fonctionnalités de l’application

Les applications de messagerie incluent le contenu d’une application dans un canal ou une conversation. Les applications d’extensibilité de réunion intègrent les applications d’un développeur au sein des réunions et offrent une expérience réactive en réunion. Pour fournir différentes fonctionnalités, les développeurs d’applications tirent parti des fonctionnalités d’application suivantes.

Les robots fournissent des réponses, des mises à jour et une assistance. Vous pouvez discuter avec ces personnes à deux ou à l’intérieur d’un canal. Ils peuvent vous aider dans le cadre de la gestion des tâches, de la planification, etc. Par exemple, vous pouvez utiliser l’application Polly pour créer des enquêtes rapides, obtenir des commentaires et vérifier le pulse.

Les onglets épinglés en haut d’un canal vous permet d’interagir avec du contenu et des services avec une expérience de qualité web.
Les connecteurs fournit du contenu et des mises à jour des services que vous utilisez fréquemment (tels que Jira Cloud et Bitbucket) directement dans une conversation de canal.

Les extensions de messagerie sont des raccourcis qui vous permet d’insérer du contenu d’application ou d’agir sur un message sans que les utilisateurs finaux n’ont à sortir de la conversation. Les extensions de messagerie peuvent utiliser des commandes de recherche qui permet aux utilisateurs finaux de trouver rapidement du contenu externe et de l’insérer dans un message ou des commandes d’action.

Pour afficher les cas d’utilisation courants mappés Teams fonctionnalités avancées, voir Maquer vos cas d’utilisation [pour Teams fonctionnalités de l’application](/microsoftteams/platform/concepts/design/map-use-cases).

<!--- TBD: Admins do many considerations and decisions around app adoption and app governance. These are to be covered in a separate article. Commenting the below content for now as part of this article revamp.

## Apps deployment decisions

Teams provides a great out-of-the-box collaboration experience for your organization, and most organizations find that the default settings work for them. This article helps you decide whether to change any of the default settings, based on your organization's profile and business requirements, then it walks you through each change. We've split the settings into two groups, starting with the core set of [changes you're more likely to make](#core-deployment-decisions). The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.

## Core deployment decisions

These are the apps settings that most organizations want to change (if the Teams default settings don't work for them).

### App availability settings

Teams provides many apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.
Get apps from the Teams Store. By default, all apps, including custom apps that you've submitted via the [Teams Store approval process](/microsoftteams/platform/publishing/apps-publish#microsoft-teams-app-approval-process), are turned on for all users. For example, users can use the Planner app to build and manage team tasks in Teams.

By default, all Microsoft-provided, third-party, and custom apps are available, and you can turn individual apps on or off. There are org-wide settings that let you turn all third-party and/or custom apps on or off for your entire organization.

| Ask yourself | Action |
|--------------|--------|
|Will you change the default Teams apps settings? | For more information about policies and settings that you can use to manage apps in your organization, see [Admin settings for apps in Microsoft Teams](admin-settings.md).|

### App permissions and other considerations

Apps are consented to by users and managed by the admin or IT pro through policies. However, app permissions and risk profile are defined in the app itself.

| Ask yourself | Action |
|--------------|--------|
|<br>Which apps do I want to allow access to? Which ones do I not want to allow access to?  | <ul><li>See [Microsoft Teams apps permissions and considerations](app-permissions.md) for a list of things you should consider when allowing access to an app, bot, tab, or connector.</li><li>See [Manage your apps in the Microsoft Teams admin center](manage-apps.md) for information about making an app available to users in your organization.</li></ul>|

--->

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
|Do I want to allow custom tabs in my organization?|For more information, see [Use built-in and custom tabs in Teams](/microsoftteams/platform/tabs/what-are-tabs).|

### Custom connectors

Connectors keep your team current by delivering content and updates from services you frequently use directly into a channel. With connectors, your Teams users can receive updates from popular services such as Trello, Wunderlist, GitHub, and Azure DevOps Services in their Teams chats.

| Ask yourself | Action |
|--------------|--------|
|Do I want to allow users to create custom connectors?|For more information, see [Use custom connectors in Teams](office-365-custom-connectors.md).|

--->

<!--- TBD: Activity reports is not part of app overview. Commenting for now. To be reused in a different article later.

### Activity reports

You can use activity reports to see how users in your organization are using Teams. For example, if some don't use Teams yet, they might not know how to get started or understand how they can use Teams to be more productive and collaborative. Your organization can use the activity reports to decide where to prioritize training and communication efforts. To view activity reports, you must be a global admin in Microsoft 365 or Office 365, Teams service admin, or Skype for Business admin.

| Ask yourself | Action |
|--------------|--------|
| <br>Who needs to see the activity reports, and do they have the correct permissions to view them? |<ul><li>If you don't want to assign an admin role to a user, you can [assign the Reports reader role](teams-activity-reports.md#reports-reader-role).</li><li>See [Roles and permissions](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [View and assign roles](/azure/active-directory/users-groups-roles/directory-manage-roles-portal) for information about assigning admin roles in Azure Active Directory.</li></ul> |

--->
