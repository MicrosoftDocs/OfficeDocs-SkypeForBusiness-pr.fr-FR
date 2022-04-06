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
ms.openlocfilehash: bb3d38060a9538196795e3da7b325840321814d8
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686391"
---
# <a name="about-apps-in-microsoft-teams"></a>À propos des applications dans Microsoft Teams

Les applications sont un excellent moyen de rassembler vos outils et services de travail et de collaborer avec d’autres personnes. Les applications aident les utilisateurs finaux à être plus productifs, collaboratifs et efficaces dans leurs tâches quotidiennes. Les organisations utilisent des applications pour se connecter à leurs clients, fournir des services et partager des informations. Les applications permettent aux utilisateurs d’être plus efficaces dans Teams conversations, réunions et canaux. Par exemple, les utilisateurs finaux utilisent un calendrier épinglé dans Teams pour collaborer rapidement avec d’autres utilisateurs, une application avec des bots qui informe les utilisateurs de QoS d’un service web dans un canal Teams, et une application pour partager et affecter des tâches à différents utilisateurs finaux dans un canal.

Notre vaste sélection d’applications validées et sécurisées dans le store fournit aux utilisateurs finaux l’accès aux outils et services dont votre organisation a besoin chaque jour. Microsoft Teams applications sont des applications SaaS web qui n’ont pas besoin d’être déployées. Les utilisateurs finaux peuvent utiliser des applications dans Teams en fonction uniquement des autorisations fournies par vous. En tant qu’administrateur, vous approuvez ou bloquez simplement l’utilisation d’une application pour les utilisateurs de votre organisation. Vous contrôlez la disponibilité des applications pour tous les utilisateurs dans les réunions, les conversations et les canaux.

Pour fournir à vos utilisateurs finaux les applications dont ils ont besoin, lisez la suite pour comprendre les types d’applications et où vos utilisateurs accèdent à ces applications. Pour en savoir plus sur l’utilisation des applications, consultez [Vue d’ensemble des applications pour les utilisateurs finaux](https://support.office.com/article/overview-of-apps-in-teams-747492ee-7cdd-4115-a993-8c7e7f98a3d0)

<!--- Commenting the previous content as part of this article revamp.

Apps let users find content from their favorite services and share it in Teams. They let you do tasks such as pin services at the top of a channel, automate notifications using bots, or share and assign tasks.

--->

Les différents types d’applications que vos utilisateurs finaux peuvent utiliser dans Teams sont les suivants :

* [Applications principales qui font partie de Teams](#core-apps).
* Autres [applications créées par Microsoft](#microsoft-provided-apps).
* [Applications tierces](#third-party-apps-validated-by-microsoft) par des partenaires (validées par Microsoft).
* [Applications personnalisées](#custom-apps) créées par votre propre organisation.

## <a name="core-apps"></a>Applications principales

Certaines fonctionnalités par défaut telles que le flux d’activité, les canaux Teams, la conversation, le calendrier et les appels sont disponibles et épinglées par défaut pour faciliter l’accès des utilisateurs finaux. En tant qu’administrateur, vous pouvez modifier le comportement par défaut à l’aide de la [stratégie d’installation](/microsoftteams/teams-app-setup-policies).

:::image type="content" source="media/core-apps-pinned1.png" alt-text="Les applications principales sont les applications épinglées dans Teams par défaut." lightbox="media/core-apps-pinned2.png":::

## <a name="microsoft-provided-apps"></a>Applications fournies par Microsoft

Microsoft fournit de nombreuses applications pour améliorer la productivité et la collaboration. Vous et les utilisateurs finaux pouvez trouver ces applications en recherchant Microsoft répertorié comme Publisher dans le Centre d’administration ou répertorié en tant que fournisseur dans le Magasin d’équipes.

Teams insère un ensemble d’applications intégrées, notamment Listes, Tâches, Compliments, Approbations, etc. Nous vous recommandons d’inclure les applications proposées Teams (par exemple, le Planificateur) dans votre déploiement initial concernant Teams.

:::image type="content" source="media/microsoft-apps-in-tac1.png" alt-text="Applications Microsoft dans Teams centre d’administration" lightbox="media/microsoft-apps-in-tac2.png":::

## <a name="third-party-apps-validated-by-microsoft"></a>Applications tierces validées par Microsoft

En plus des applications fournies par Microsoft, vous pouvez utiliser des applications tierces validées par Microsoft. Microsoft valide les fonctionnalités et la sécurité de ces applications avant de les rendre disponibles dans Teams magasin. Pour comprendre les avantages de la validation d’application, consultez [la validation des applications tierces](overview-of-app-validation.md).

:::image type="content" source="media/3p-apps-in-teams.png" alt-text="Exemple d’applications tierces dans Teams store":::

## <a name="custom-apps"></a>Applications personnalisées

Les applications créées par les développeurs de votre organisation sont appelées applications personnalisées. Le développement d’une telle application est commandé pour des exigences spécifiques de votre organisation et vous disposez de contrôles pour autoriser ou interdire ces applications. Les développeurs de votre organisation peuvent rapidement créer des solutions à faible code personnalisées à l’aide de Teams intégration à [Microsoft Power Platform](/microsoftteams/platform/samples/teams-low-code-solutions).

Une fois qu’un administrateur autorise l’utilisation d’applications personnalisées, les utilisateurs finaux recherchent ces applications en cliquant sur **Intégré pour votre organisation** dans le volet de navigation gauche de Teams magasin.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Applications personnalisées dans Teams Store dans Teams application de bureau" lightbox="media/built-for-your-org2.png":::

### <a name="understand-sideloading-of-custom-apps"></a>Comprendre le chargement indépendant des applications personnalisées

Lors du développement d’applications personnalisées et avant de les distribuer aux utilisateurs finaux, les développeurs testent les applications en les ajoutant au Store pour les tester par eux-mêmes ou avec une équipe dans laquelle ils chargent l’application de manière indépendante. Cette méthode est appelée chargement indépendant des applications et s’applique uniquement aux applications personnalisées.

Les développeurs peuvent charger une application de manière à la rendre disponible pour les membres d’une équipe spécifique, généralement pour tester une application en cours de développement. Cela ne nécessite pas l’approbation de l’administrateur si le chargement indépendant est autorisé. En tant qu’administrateur, vous pouvez interdire le chargement indépendant pour n’importe quel développeur.

Si vous interdisez le chargement indépendant, les développeurs peuvent toujours tester leurs applications dans un [locataire de test](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Une fois le développement d’applications personnalisé terminé, les développeurs demandent aux administrateurs de distribuer leur application personnalisée aux utilisateurs finaux. Pour plus d’informations, voir [comment publier une application personnalisée](/microsoftteams/upload-custom-apps). En tant qu’administrateur, vous pouvez autoriser ou interdire l’utilisation d’une application personnalisée pour des utilisateurs spécifiques.

### <a name="about-app-templates"></a>À propos des modèles d’application

Les modèles d’application pour Teams sont des exemples d’applications fonctionnels prêts pour la production créés par Microsoft pour illustrer les cas d’usage courants, présenter les meilleures pratiques de développement d’applications et fournir des applications open source que les développeurs peuvent étendre pour créer des applications personnalisées. Les développeurs de votre organisation personnalisent les modèles d’application pour les besoins de votre organisation en modifiant simplement le code disponible dans GitHub. En tant qu’administrateur, vous fournissez ces applications en tant qu’applications personnalisées pour vos utilisateurs finaux.

Pour en savoir plus, consultez [Microsoft Teams modèles d’application](https://adoption.microsoft.com/microsoft-teams/app-templates/).

## <a name="understand-app-capabilities"></a>Comprendre les fonctionnalités de l’application

Pour offrir des expériences riches qui permettent aux utilisateurs finaux de travailler dans Teams, les développeurs d’applications tirent parti des fonctionnalités d’application suivantes. Les extensions de messagerie permettent aux utilisateurs d’interagir avec votre service web Teams client. Ils recherchent ou démarrent des actions dans un système externe. Vous pouvez envoyer le résultat de l’interaction au client Teams en tant que carte richement mise en forme. Les applications d’extensibilité de réunion intègrent les applications d’un développeur dans les réunions et offrent une expérience de réunion réactive.

Les bots sont également appelés chatbot ou bot conversationnel. Il s’agit d’une application qui exécute des tâches simples et répétitives. Une interaction de bot peut être une question et une réponse rapides, ou il peut s’agir d’une conversation complexe qui fournit l’accès aux services ou à l’assistance. Les utilisateurs peuvent discuter avec un peu un-à-un ou dans un canal. Par exemple, vous pouvez utiliser l’application Polly pour créer des enquêtes rapides, obtenir des commentaires et effectuer une vérification du pouls.

Les onglets sont Teams pages web sensibles épinglées en haut d’un canal ou d’une conversation. Les onglets vous permettent d’interagir avec du contenu et des services avec une expérience web. Vous pouvez ajouter des onglets dans le cadre d’un canal au sein d’une équipe, d’une conversation de groupe ou d’une application personnelle pour un utilisateur individuel.

Les webhooks et connecteurs fournissent du contenu et des mises à jour à partir de services que les utilisateurs finaux utilisent fréquemment (tels que Jira Cloud et Bitbucket) directement dans une conversation de canal. Les applications qui utilisent cette fonctionnalité peuvent communiquer avec des applications externes et peuvent envoyer ou recevoir des notifications et des messages à partir d’un service externe.

Les extensions de messagerie sont des raccourcis permettant d’insérer du contenu d’application ou d’agir sur un message sans que les utilisateurs finaux n’ont à s’éloigner de la conversation. Les extensions de messagerie peuvent avoir des commandes de recherche permettant aux utilisateurs finaux de trouver rapidement du contenu externe et de l’insérer dans un message ou des commandes d’action.

Pour afficher les cas d’usage courants mappés à Teams fonctionnalités, consultez [Mapper vos cas d’utilisation à Teams fonctionnalités d’application](/microsoftteams/platform/concepts/design/map-use-cases).

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
