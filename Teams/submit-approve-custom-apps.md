---
title: Utiliser l’API de soumission d’applications teams pour soumettre et approuver vos applications personnalisées
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: joglocke, vaibhava
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment approuver vos applications personnalisées envoyées à l’aide de l’API de soumission d’applications teams dans Microsoft Teams.
ms.openlocfilehash: 5b6c8512943527a82b3477579e535bcc151331c0
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731092"
---
# <a name="publish-a-custom-app-submitted-through-the-teams-app-submission-api"></a>Publier une application personnalisée soumise par le biais de l’API de soumission d’applications teams

## <a name="overview"></a>Vue d’ensemble

> [!NOTE]
> Lorsque vous publiez une application teams personnalisée, celle-ci est disponible pour les utilisateurs du magasin d’applications de votre organisation. Il existe deux façons de publier une application personnalisée et votre mode d’utilisation dépend de la manière dont vous obtenez l’application. **Cet article décrit l’approbation et la publication d’une application personnalisée soumise par un développeur à l’aide de l’API de soumission d’applications teams**. Quant à l’autre méthode, le téléchargement d’une application personnalisée est utilisé lorsqu’un développeur vous envoie un package d’application au format. zip. Pour en savoir plus sur cette méthode, voir <a href="https://docs.microsoft.com/microsoftteams/upload-custom-apps" target="_blank">publier une application personnalisée en chargeant un package d’application</a>.

Cet article fournit des instructions complètes sur la façon de faire de votre application teams le déploiement vers la découverte. Vous obtenez une vue d’ensemble des expériences connectées fournies par teams dans le cycle de vie de l’application pour rationaliser le développement, le déploiement et la gestion des applications personnalisées dans le magasin d’applications de votre organisation.

Nous allons aborder chacune des étapes du cycle de vie, y compris la façon dont les développeurs peuvent utiliser l’API de soumission d’applications teams pour soumettre directement des applications personnalisées au centre d’administration de Microsoft Teams, afin que vous puissiez passer en revue et approuver des applications pour les utilisateurs de votre organisation, et la façon dont les utilisateurs les découvrent dans Teams.

![Vue d’ensemble de votre application du développement au déploiement](media/custom-app-lifecycle.png)

Ce guide est axé sur les aspects de l’application équipes et est destiné aux administrateurs et aux professionnels de l’informatique. Pour plus d’informations sur le développement d’applications Teams, voir la documentation pour les <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">développeurs teams</a>.

## <a name="develop"></a>Développer

### <a name="create-the-app"></a>Créer l’application

La plateforme de développement Microsoft teams permet aux développeurs d’intégrer facilement vos propres applications et services pour améliorer votre productivité, prendre des décisions plus rapidement et collaborer sur du contenu et des flux de travail existants. Les applications développées sur la plateforme teams sont des ponts entre le client teams et vos services et flux de travail, qui les relient directement dans le contexte de votre plate-forme de collaboration. Pour plus d’informations, consultez la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentation du développeur teams</a>.

### <a name="submit-the-app"></a>Envoi de l’application

Lorsque l’application est prête à être utilisée en production, le développeur peut soumettre l’application à l’aide de l’API de soumission d’application Teams, qui peut être appelée à partir de l' <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">API de Graph</a>, d’un environnement de développement intégré (IDE) tel que le code Visual Studio ou d’une plateforme telle que les applications Power et les agents de la gestion des applications virtuelles. Pour cela, l’application est disponible dans la page <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">gérer les applications</a> du centre d’administration Microsoft Teams, où vous, l’administrateur, pouvez la consulter et l’approuver.

L’API de soumission d’application Teams, <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">conçue sur Microsoft Graph</a>, permet à votre organisation de se développer sur la plateforme de votre choix et d’automatiser le processus de soumission à approbation des applications personnalisées sur Teams.

Voici un exemple de l’étape de soumission de l’application dans le code Visual Studio :

![envoi d’une application dans le code Visual Studio](media/custom-app-lifecycle-submit-app.png)

Gardez à l’esprit que cette opération ne publie pas encore l’application dans le magasin d’applications de votre organisation. Cette étape envoie l’application au centre d’administration Microsoft Teams, où vous pouvez l’approuver pour la publication dans le magasin d’applications de votre organisation.

Pour plus d’informations sur l’utilisation de l’API Graph pour proposer des applications, voir <a href="https://docs.microsoft.com/graph/api/teamsapp-publish?view=graph-rest-1.0&tabs=http#example-2-upload-a-new-application-for-review-to-an-organizations-app-catalog" target="_blank">cet article</a>.

## <a name="validate"></a>Invalidé

La page <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">gérer les applications</a> dans le centre d’administration de Microsoft Teams (dans le volet de navigation gauche, accédez à applications d' **équipe**  >  **gérer** les applications), vous donne un aperçu de toutes les applications teams pour votre organisation. Le widget **approbation en attente** en haut de la page vous permet de savoir quand une application personnalisée est soumise pour approbation.

Dans le tableau, une application nouvellement soumise affiche automatiquement l' **État** de publication **soumis** et **statut** de **blocage**. Vous pouvez trier la colonne **État de publication** dans l’ordre décroissant pour trouver rapidement l’application.

![État de publication ](media/custom-app-lifecycle-validate-app.png)

Cliquez sur le nom de l’application pour accéder à la page des détails de l’application. Dans l’onglet **à propos** de, vous pouvez afficher des détails sur l’application, notamment sa description, son état, son sous-état et son ID d’application.

! page Détails de l’application pour une application soumise] (média/custom-app-lifecycle-app-details.png)

Pour plus d’informations sur l’utilisation de l’API de graphique pour vérifier l' **État de publication**, voir <a href="https://docs.microsoft.com/graph/api/teamsapp-list?view=graph-rest-1.0&tabs=http#example-3-list-applications-with-a-given-id-and-return-the-submission-review-state" target="_blank">cet article</a>.

## <a name="publish"></a>Publi

Lorsque vous êtes prêt à mettre l’application à la disposition des utilisateurs, publiez l’application.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage** apps.
2. Cliquez sur le nom de l’application pour accéder à la page Détails de l’application, puis dans la zone **État de publication** , sélectionnez **publier**.

    Après la publication de l’application, l' **État de publication** devient **publié** et le **statut** est automatiquement **autorisé**.

## <a name="set-up-and-manage"></a>Configurer et gérer

### <a name="control-access-to-the-app"></a>Contrôler l’accès à l’application

Par défaut, tous les utilisateurs de votre organisation peuvent accéder à l’application dans le magasin d’applications de votre organisation. Pour restreindre et contrôler les personnes autorisées à utiliser l’application, vous pouvez créer et affecter une stratégie d’autorisations d’application. Pour en savoir plus, voir <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">gérer les stratégies d’autorisation d’applications dans Microsoft teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Épingler et installer l’application pour détecter les utilisateurs

Par défaut, pour que les utilisateurs puissent trouver l’application, ils doivent accéder au magasin d’applications de votre organisation et rechercher celles-ci. Pour permettre aux utilisateurs d’accéder facilement à l’application, vous pouvez épingler l’application à la barre de l’application dans Teams. Pour ce faire, créez une stratégie de configuration d’application et attribuez-la à des utilisateurs. Pour en savoir plus, voir <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">gérer les stratégies de configuration des applications dans Microsoft teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Effectuer une recherche dans le journal d’audit pour les événements d’application teams

Vous pouvez effectuer une recherche dans le journal d’audit pour afficher l’activité des applications teams au sein de votre organisation. Pour en savoir plus sur la façon d’effectuer une recherche dans le journal d’audit et d’afficher la liste des activités d’équipe qui sont enregistrées dans le journal d’audit, voir <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Rechercher des événements dans le journal d’audit dans teams</a>.

Pour pouvoir effectuer une recherche dans le journal d’audit, vous devez d’abord activer l’audit dans le <a href="https://protection.office.com" target="_blank">Centre de sécurité & conformité</a>. Pour plus d’informations, voir <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">activer ou désactiver la recherche dans le journal d’audit</a>. Gardez à l’esprit que les données d’audit sont uniquement disponibles à partir du point d’activation de l’audit.

## <a name="discover-and-adopt"></a>Découvrir et adopter

Les utilisateurs disposant de droits d’accès à l’application peuvent les trouver dans le magasin d’applications de votre organisation. Accédez au **nom conçu pour le *nom de votre organisation*** dans la page applications pour trouver les applications personnalisées de votre organisation.

![Page applications indiquant l’application publiée ](media/custom-app-lifecycle-discovery.png)

Si vous avez créé et affecté une stratégie de configuration de l’application, l’application est épinglée à la barre de l’application dans teams pour faciliter l’accès aux utilisateurs qui ont reçu la stratégie.

## <a name="update"></a>Mettre à jour

Pour mettre à jour une application, les développeurs doivent continuer à suivre les étapes décrites dans la section [développer](#develop) .

Lorsque le développeur envoie une mise à jour à une application personnalisée publiée, vous recevez une notification dans le widget **approbation en attente** de la page <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">gérer les applications</a> . Dans la table, l' **État de publication** de l’application est défini sur **mise à jour soumise**.

![Page gérer les applications affichant les demandes en attente et l’état de l’application ](media/custom-app-lifecycle-update-submitted.png)

Pour consulter et publier une mise à jour d’application :

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage** apps.
2. Cliquez sur le nom de l’application pour accéder à la page des détails de l’application, puis sélectionnez **mettre à jour disponible** pour consulter les détails de la mise à jour.

    ![page Détails de l’application](media/custom-app-lifecycle-update-app.png)
3. Lorsque vous êtes prêt, sélectionnez **publier** pour publier la mise à jour. Cette opération a pour effet de remplacer l’application existante, de mettre à jour le numéro de version et de changer l' **État de publication** en **publiée**. Toutes les stratégies d’autorisation d’application et les stratégies de configuration des applications restent appliquées pour l’application mise à jour.

    Si vous refusez la mise à jour, la version antérieure de l’application reste publiée.

Gardez à l’esprit les points suivants :

- Lorsqu’une application est approuvée, une mise à jour de l’application peut être soumise à une application. Cela signifie que les développeurs ayant soumis l’application à l’origine de l’application peuvent soumettre une mise à jour de l’application.
- Lorsqu’un développeur envoie une application et que celle-ci est en attente, seul ce même développeur peut proposer une mise à jour de l’application. Les autres développeurs peuvent uniquement mettre à jour une fois que l’application est approuvée.

Pour plus d’informations sur l’utilisation de l’API de graphique pour mettre à jour des applications, voir <a href="https://docs.microsoft.com/graph/api/teamsapp-update?view=graph-rest-1.0#example-2-update-a-previously-reviewed-and-published-application-to-the-teams-app-catalog" target="_blank">cet article</a>.

### <a name="update-experience-for-users"></a>Mise à jour de l’interface utilisateur

Dans la plupart des cas, une fois que vous avez publié une mise à jour de l’application, la nouvelle version s’affiche automatiquement pour les utilisateurs. Il y a toutefois des mises à jour du <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">manifeste Microsoft teams</a> qui nécessitent l’acceptation de l’utilisateur :

* Un bot a été ajouté ou supprimé
* Modification de la propriété « botId » d’une bot existante
* Modification de la propriété « isNotificationOnly » d’une bot existante
* La propriété « supportsFiles » du bot a changé
* Ajout ou suppression d’une extension de messagerie
* Un nouveau connecteur a été ajouté.
* Un nouvel onglet statique a été ajouté.
* Un nouvel onglet configurable a été ajouté.
* Propriétés dans « webApplicationInfo » modifiées

![nouvelle version disponible](media/manage-your-custom-apps-update1.png)

![option de mise à niveau pour une application](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Sujets associés

- [Publier une application personnalisée en chargeant un package d’application](upload-custom-apps.md)
- [Gérer vos applications dans le centre d’administration Microsoft teams](manage-apps.md)
- [Gérer les stratégies d’application personnalisée et les paramètres dans Teams](teams-custom-app-policies-and-settings.md)
- [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
- [Gérer les stratégies de mise en application dans Teams](teams-app-setup-policies.md)
- <a href="https://docs.microsoft.com/graph/api/resources/teamsapp?view=graph-rest-1.0" target="_blank">API Microsoft Graph pour les applications teams</a>
