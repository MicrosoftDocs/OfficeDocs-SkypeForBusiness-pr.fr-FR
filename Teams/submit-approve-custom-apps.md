---
title: Utiliser l’API de soumission d’applications Teams pour envoyer et approuver vos applications personnalisées
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment approuver vos applications personnalisées envoyées à l’aide de l’API de soumission d’applications Teams dans Microsoft Teams.
ms.openlocfilehash: 644e4afd28dbec27385516ce3e0676eb9ea27ef1
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837524"
---
# <a name="publish-a-custom-app-submitted-using-the-teams-app-submission-api"></a>Publier une application personnalisée envoyée à l’aide de l’API de soumission d’application Teams

Cet article fournit des conseils de bout en bout sur la façon de faire passer votre application Teams du développement au déploiement en passant par la découverte. Vous obtiendrez une vue d’ensemble des expériences connectées fournies par Teams tout au long du cycle de vie des applications pour simplifier le développement, le déploiement et la gestion d’applications personnalisées dans l’App Store de votre organisation.

Nous aborderons chaque étape du cycle de vie, notamment la façon dont les développeurs peuvent utiliser l’API de soumission d’applications Teams pour envoyer des applications personnalisées directement au Centre d’administration Microsoft Teams pour que vous puissiez les examiner et les approuver, comment définir des stratégies pour gérer les applications pour les utilisateurs de votre organisation et comment vos utilisateurs les découvrent dans Teams.

:::image type="content" source="media/custom-app-lifecycle.png" alt-text="Vue d’ensemble de votre application du développement au déploiement":::

Ces conseils se concentrent sur les aspects Teams de l’application et sont destinés aux administrateurs et aux professionnels de l’informatique. Pour plus d’informations sur le développement d’applications Teams, consultez la [documentation du développeur Teams](/microsoftteams/platform).

> [!NOTE]
> Lorsque vous publiez une application Teams personnalisée, elle est disponible pour les utilisateurs de l’App Store de votre organisation. Il existe deux façons de publier une application personnalisée et la façon dont vous l’utilisez dépend de la façon dont vous obtenez l’application. Cet article se concentre sur la façon d’approuver et de publier une application personnalisée qu’un développeur envoie via l’API de soumission d’application Teams. L’autre méthode, le chargement d’une application personnalisée, est utilisée lorsqu’un développeur vous envoie un package d’application au format .zip. Pour en savoir plus sur cette méthode, consultez [Publier une application personnalisée en chargeant un package d’application](/microsoftteams/upload-custom-apps). Le widget Approuver l’application n’est pas disponible dans les locataires GCC.

> [!IMPORTANT]
> Cette méthode n’est pas disponible dans les environnements GCC. [Chargez une application personnalisée](upload-custom-apps.md) pour la publier dans des environnements GCC.

## <a name="develop"></a>Développer

### <a name="create-the-app"></a>Créer l’application

La plateforme de développement Microsoft Teams permet aux développeurs d’intégrer facilement vos propres applications et services afin d’améliorer la productivité, de prendre des décisions plus rapidement et de créer une collaboration autour du contenu et des flux de travail existants. Les applications basées sur la plateforme Teams sont des ponts entre le client Teams et vos services et flux de travail, en les intégrant directement dans le contexte de votre plateforme de collaboration. Pour plus d’informations, consultez la [documentation du développeur Teams](/microsoftteams/platform).

### <a name="submit-the-app"></a>Envoyer l’application

Lorsque l’application est prête à être utilisée en production, le développeur peut envoyer l’application à l’aide de l’API de soumission d’application Teams, qui peut être appelée à partir de [API Graph](/graph/api/teamsapp-publish?view=graph-rest-beta&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), d’un environnement de développement intégré (IDE) tel que Visual Studio Code ou d’une plateforme telle que Power Apps et Power Virtual Agents. Cela rend l’application disponible sur la page [Gérer les applications](/microsoftteams/manage-apps) du Centre d’administration Teams, où vous pouvez la consulter et l’approuver.

L’API de soumission d’applications Teams, [basée sur Microsoft Graph](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true), permet à votre organisation de se développer sur la plateforme de votre choix et automatise le processus de soumission à l’approbation pour les applications personnalisées sur Teams.

Voici un exemple de l’aspect de cette étape de soumission d’application dans Visual Studio Code :

:::image type="content" source="media/custom-app-lifecycle-submit-app.png" alt-text="Capture d’écran de la soumission d’application dans Visual Studio Code.":::

N’oubliez pas que cela ne publie pas encore l’application dans l’App Store de votre organisation. Cette étape envoie l’application au Centre d’administration Teams, où vous pouvez l’approuver pour la publication dans l’App Store de votre organisation.

Pour plus d’informations sur l’utilisation de la API Graph pour envoyer des applications, voir [ici](/graph/api/teamsapp-publish?tabs=http&view=graph-rest-beta#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog&preserve-view=true).

## <a name="notify"></a>Prévenir

Vous pouvez activer les notifications afin de savoir quand les développeurs soumettent une nouvelle application pour révision et approbation. Vous recevrez également des notifications lorsque les développeurs soumettent des mises à jour d’application. Pour activer les notifications de soumission d’application dans le Centre d’administration Teams, accédez à **Notifications & alertes** > **[et](https://admin.teams.microsoft.com/notifications/rules)** >  activez la règle en remplaçant l’état **Actif**. Par défaut, ce paramètre est désactivé. Vous devez être administrateur général ou administrateur Teams pour activer ce paramètre.

Une fois ce paramètre activé, vous recevez des notifications dans l’équipe **alertes et notifications Administration** sous un nouveau canal nommé **Soumissions d’applications**. Vous pouvez également choisir une équipe et un canal existants pour recevoir des notifications envoyées à une équipe et un canal spécifiés. Pour cela, merci de procéder comme suit :

1. Dans la règle **soumissions d’applications** , cochez la case **d’alerte de canal** sous **Actions**.
1. Choisissez le bouton **Sélectionner un canal** .
1. Recherchez une équipe à ajouter.
1. Recherchez un canal à ajouter.
1. Sélectionnez **Appliquer**.

   :::image type="content" source="media/channel-alert.png" alt-text="Case à cocher de notification d’alerte de canal personnalisé." lightbox="media/channel-alert.png":::

> [!NOTE]
> Cochez la case **d’alerte de canal par défaut** pour recevoir des notifications à l’équipe **alertes et notifications Administration** dans le canal **Soumissions d’applications**.

:::image type="content" source="media/default-channel-alert.png" alt-text="Case à cocher de notification d’alerte de canal par défaut." lightbox="media/default-channel-alert.png":::

Vous pouvez également configurer des notifications sur un webhook externe en spécifiant une URL de webhook public après avoir coché la case **Webhook** . Une charge utile de notification JSON est envoyée à votre URL de webhook.

:::image type="content" source="media/app-submission-notification.png" alt-text="Notification de soumission d’application." lightbox="media/app-submission-notification.png":::

Après avoir configuré la règle de soumission d’application, vous pouvez passer en revue les cartes de notification dans le canal spécifié pour afficher les détails de l’application et sélectionner **Afficher les détails** pour ouvrir les applications dans le Centre d’administration Teams.

## <a name="validate"></a>Valider

La page [Gérer les applications](/microsoftteams/manage-apps) dans le Centre d’administration Teams (dans la navigation de gauche, accédez à [**Gérer** les **applications** >  Teams](https://admin.teams.microsoft.com/manage-apps)), vous donne une vue de toutes les applications Teams pour votre organisation. Le widget **d’approbation en attente** en haut de la page vous indique quand une application personnalisée est soumise pour approbation.

Dans le tableau, une application nouvellement soumise affiche automatiquement **l’état Publication** de **l’état Soumis** et **l’état** **de l’application Bloquée**. Vous pouvez trier la colonne **d’état Publication** dans l’ordre décroissant pour trouver rapidement l’application.

:::image type="content" source="media/custom-app-lifecycle-validate-app.png" alt-text="État de publication." lightbox="media/custom-app-lifecycle-validate-app.png":::

Cliquez sur le nom de l’application pour accéder à la page de détails de l’application. Sous l’onglet **À propos** , vous pouvez afficher des détails sur l’application, notamment la description, l’état, l’expéditeur et l’ID d’application.

:::image type="content" source="media/custom-app-lifecycle-app-details.png" alt-text="Page détails de l’application pour une application envoyée." lightbox="media/custom-app-lifecycle-app-details.png":::

Pour plus d’informations sur l’utilisation de la API Graph pour vérifier **l’état de** publication, voir [ici](/graph/api/appcatalogs-list-teamsapps?tabs=http&view=graph-rest-beta#example-3-find-application-based-on-the-teams-app-manifest-id&preserve-view=true).

## <a name="publish"></a>Publier

Lorsque vous êtes prêt à mettre l’application à la disposition des utilisateurs, publiez l’application.

1. Connectez-vous au Centre d’administration Teams et accédez aux **applications** >  Teams **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Sélectionnez le nom de l’application pour accéder à la page de détails de l’application, puis dans la zone **d’état Publication** , sélectionnez **Publier**.

    :::image type="content" source="media/submitted-app-pending-action.png" alt-text="Bouton Publier sur la page de détails de l’application.":::

Après la publication de l’application, **l’état Publication** devient **Publié** et **l’état** devient **Autorisé**.

## <a name="set-up-and-manage"></a>Configurer et gérer

### <a name="control-access-to-the-app"></a>Contrôler l’accès à l’application

Par défaut, tous les utilisateurs de votre organisation peuvent accéder à l’application dans l’App Store de votre organisation. Pour restreindre et contrôler qui a l’autorisation d’utiliser l’application, vous pouvez créer et attribuer une stratégie d’autorisation d’application. Pour plus d’informations, consultez [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Épinglez et installez l'application pour que les utilisateurs la découvrent.

Par défaut, pour que les utilisateurs trouvent l’application, ils doivent accéder à l’App Store de votre organisation et la rechercher. Pour permettre aux utilisateurs d’accéder facilement à l’application, vous pouvez épingler l’application à la barre de l’application dans Teams. Pour ce faire, créez une stratégie de configuration d’application et attribuez-la aux utilisateurs. Pour plus d’informations, consultez l’article [Gérer les stratégies et paramètres d’application personnalisés dans Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Rechercher des événements d’application dans les journaux d’audit

Vous pouvez effectuer une recherche dans le journal d'audit pour visualiser l'activité des applications Teams dans votre organisation. Pour en savoir plus sur la recherche dans le journal d’audit et pour afficher la liste des activités Teams qui sont enregistrées dans le journal d’audit, consultez [Rechercher des événements dans Teams dans le journal d’audit](audit-log-events.md).

Pour effectuer une recherche dans le journal d’audit, vous devez au préalable activer la fonctionnalité d’audit dans le [Centre de sécurité et de conformité](https://sip.protection.office.com/). Si vous souhaitez en savoir plus, veuillez consulter [Activer ou désactiver la recherche dans le journal d'audit](/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&preserve-view=true). N’oubliez pas que les données d’audit ne sont disponibles qu’à partir du moment où vous avez activé l’audit.

## <a name="discover-and-adopt"></a>Découvrir et adopter

Les utilisateurs disposant d’autorisations sur l’application peuvent la trouver dans l’App Store de votre organisation. Accédez à **Construire pour *Le nom de votre organisation*** dans la page Applications pour rechercher les applications personnalisées de votre organisation.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Page Applications montrant l’application publiée." lightbox="media/custom-app-lifecycle-discovery.png":::

Si vous avez créé et attribué une stratégie d’installation d’application, l’application est épinglée à la barre des applications dans Teams pour faciliter l’accès aux utilisateurs auxquels la stratégie a été attribuée.

## <a name="update"></a>Mettre à jour

Pour mettre à jour une application, les développeurs doivent continuer à suivre les étapes décrites dans la section [Développer](#develop) .

Lorsque le développeur soumet une mise à jour à une application personnalisée publiée, vous êtes averti dans le widget **d’approbation en attente** de la page [Gérer les applications](/microsoftteams/manage-apps) . Dans le tableau, **l’état de publication** de l’application est défini sur **Mise à jour envoyée**. Vous serez également averti dans l’équipe **Administration Alertes et Notifications** sous le canal de **soumission** d’application si vous avez activé les notifications de soumission d’application. La carte de notification comporte un lien vous permettant de vous rendre directement à l’application dans le Centre d’administration Teams. Pour plus d’informations sur l’activation des notifications de soumission d’application, consultez [Notification](#notify).

:::image type="content" source="media/custom-app-lifecycle-update-submitted.png" alt-text="Page Gérer les applications montrant les demandes en attente et l’état de l’application." lightbox="media/custom-app-lifecycle-update-submitted.png":::

Pour passer en revue et publier une mise à jour d’application :

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Applications Teams** > **Gérer les applications**.
1. Cliquez sur le nom de l’application pour accéder à la page de détails de l’application, puis sélectionnez **Mettre à jour disponible** pour passer en revue les détails de la mise à jour.

   :::image type="content" source="media/custom-app-lifecycle-update-app.png" alt-text="Page détails de l’application." lightbox="media/custom-app-lifecycle-update-app.png":::

1. Lorsque vous êtes prêt, sélectionnez **Publier** pour publier la mise à jour. Cette opération remplace l’application existante, met à jour le numéro de version et remplace **l’état publication** **par Publié**. Toutes les stratégies d’autorisation d’application et les stratégies d’installation d’application restent appliquées pour l’application mise à jour.

    Si vous refusez la mise à jour, la version antérieure de l’application reste publiée.

Gardez à l’esprit les éléments suivants :

* Lorsqu’une application est approuvée, n’importe quel utilisateur peut envoyer une mise à jour à l’application. Cela signifie que d’autres développeurs, y compris le développeur qui a envoyé l’application à l’origine, peuvent envoyer une mise à jour à l’application.
* Lorsqu’un développeur envoie une application et que la demande est en attente, seul ce même développeur peut envoyer une mise à jour à l’application. D’autres développeurs ne peuvent soumettre une mise à jour qu’une fois l’application approuvée.

Pour plus d’informations sur l’utilisation de la API Graph pour mettre à jour des applications, voir [ici](/graph/api/teamsapp-update?view=graph-rest-1.0&tabs=http&preserve-view=true).

## <a name="related-articles"></a>Articles connexes

* [Publier une application personnalisée en téléchargeant un package d’application](upload-custom-apps.md)
* Vous gérez les applications pour votre organisation dans les [applications Teams au sein du centre d’administration Microsoft Teams](manage-apps.md).
* [Gérer les stratégies d’application personnalisée et les paramètres dans Teams](teams-custom-app-policies-and-settings.md)
* [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
* [Gérer les stratégies de mise en application dans Teams](teams-app-setup-policies.md)
* [Surveillance et alertes Teams](alerts/teams-admin-alerts.md)
* [Applications Microsoft API Graph pour Teams](alerts/teams-admin-alerts.md)
