---
title: Télécharger vos applications personnalisées dans le centre d’administration Microsoft teams
author: lanachin
ms.author: v-lanac
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
description: Découvrez comment télécharger vos applications personnalisées dans le magasin d’applications de votre organisation dans le centre d’administration Microsoft Teams.
ms.openlocfilehash: d43b19f4ada3ce6f0424a324cdea6f194575325b
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583643"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Publier une application personnalisée en chargeant un package d’application

> [!NOTE]
> Lorsque vous publiez une application teams personnalisée, celle-ci est disponible pour les utilisateurs du magasin d’applications de votre organisation. Il existe deux façons de publier une application personnalisée et votre mode d’utilisation dépend de la manière dont vous obtenez l’application. **Cet article décrit comment publier une application personnalisée en chargeant un package d’application (au format. zip) qu’un développeur vous envoie**. En revanche, l’approbation d’une application personnalisée est utilisée lorsqu’un développeur soumet une application directement à la page <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Manage Apps</a> par le biais de l’API de soumission d’applications Teams. Pour en savoir plus sur cette méthode, voir <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">publier une application personnalisée soumise par le biais de l’API de soumission d’applications teams</a>.

Cet article fournit des instructions complètes sur la façon de faire de votre application teams le déploiement vers la découverte. Ce guide est axé sur les aspects de l’application équipes et est destiné aux administrateurs et aux professionnels de l’informatique. Pour plus d’informations sur le développement d’applications Teams, voir la documentation pour les <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">développeurs teams</a>.

![Vue d’ensemble de votre application du développement au déploiement](media/upload-custom-apps.png)

## <a name="develop"></a>Développer

### <a name="create-your-app"></a>Créer votre application

La plateforme de développement Microsoft teams permet aux développeurs d’intégrer facilement vos propres applications et services pour améliorer votre productivité, prendre des décisions plus rapidement et collaborer sur du contenu et des flux de travail existants. Les applications développées sur la plateforme teams sont des ponts entre le client teams et vos services et flux de travail, qui les relient directement dans le contexte de votre plate-forme de collaboration. Pour plus d’informations, consultez la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentation du développeur teams</a>.

## <a name="validate"></a>Invalidé

### <a name="get-the-app-package"></a>Télécharger le package de l’application

Lorsque l’application est prête à être utilisée en production, le développeur doit produire un package d’application. Ils peuvent utiliser <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">app Studio</a> pour cela. Elle vous envoie le fichier au format. zip.

Microsoft utilise <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">ces instructions</a> pour s’assurer de la conformité des applications avec les normes de qualité et de sécurité du magasin des applications globales Teams.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Permettre aux utilisateurs approuvés de télécharger des applications personnalisées

Pour vérifier que l’application fonctionne correctement dans votre client de production, vous devez permettre aux utilisateurs approuvés et/ou approuvés de télécharger des applications personnalisées dans le client de production. Pour ce faire, vous devez utiliser les <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">stratégies de configuration d’applications</a> .

> [!NOTE]
> Si vous n’avez pas l’habitude de télécharger l’application sur votre client de production pour la validation, même pour les utilisateurs vous-même ou approuvés, vous pouvez ignorer cette étape et suivre les étapes des sections [Télécharger](#upload) et [configurer et gérer](#set-up-and-manage) pour publier l’application non validée dans le magasin d’applications de votre organisation. Restreignez ensuite l’accès à cette application uniquement et aux utilisateurs approuvés. Ces utilisateurs peuvent ensuite obtenir l’application auprès du magasin d’applications de votre organisation pour effectuer la validation. Une fois l’application validée, utilisez les mêmes stratégies d’autorisation pour ouvrir Access et annuler l’application en vue d’une utilisation en production.

Pour permettre aux utilisateurs approuvés de télécharger des applications personnalisées, procédez comme suit :

1. Activez le paramètre **autoriser l’interaction avec les applications personnalisées** à l’échelle de l’organisation. Pour ce faire :
    1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage Apps**, puis cliquez sur **paramètres de l’application à l’échelle**de l’organisation.
    2. Sous **applications personnalisées**, activez **autoriser l’interaction avec les applications personnalisées**, puis cliquez sur **Enregistrer**.
2. Désactivez le paramètre **Télécharger des applications personnalisées** de la stratégie de configuration de l’application globale. Pour ce faire :
    1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à stratégies de configuration des **applications**  >  **d'** équipe, puis cliquez sur la stratégie **globale par défaut** de l’organisation.
    2. Désactivez l’option **Télécharger les applications personnalisées**, puis cliquez sur **Enregistrer**.
3. Créez une stratégie de configuration de l’application qui permet le téléchargement d’applications personnalisées et l’attribution à votre ensemble d’utilisateurs approuvés. Pour ce faire :
    1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à stratégies de configuration des **applications**  >  **d'** équipe, puis cliquez sur **Ajouter**. Donnez un nom et une description à la nouvelle stratégie, activez l' **application télécharger des applications personnalisées**, puis cliquez sur **Enregistrer**.
    2. Sélectionnez la nouvelle stratégie que vous avez créée, puis cliquez sur **gérer les utilisateurs**. Recherchez un utilisateur, cliquez sur **Ajouter**, puis sur **appliquer**. Répétez cette étape pour affecter la stratégie à l’ensemble de vos utilisateurs approuvés.

        ![Capture d’écran de la page « Ajouter une stratégie de configuration de l’application »](media/manage-your-lob-apps-new-app-setup-policy.png)

    Ces utilisateurs peuvent désormais télécharger le manifeste de l’application pour vérifier que l’application fonctionne correctement dans le client de production.

## <a name="upload"></a>Télécharge

Pour mettre l’application à la disposition des utilisateurs figurant dans le magasin d’applications de votre organisation, téléchargez l’application. Vous pouvez le faire dans la page <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">gérer les applications</a> du centre d’administration Microsoft Teams.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage**apps.
2. Cliquez sur **Télécharger**, sur **Sélectionner un fichier**, puis sélectionnez le package d’application reçu du développeur.

   ![Capture d’écran du téléchargement d’une application dans le centre d’administration](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Configurer et gérer

### <a name="control-access-to-the-app"></a>Contrôler l’accès à l’application

Par défaut, tous les utilisateurs de votre organisation peuvent accéder à l’application dans le magasin d’applications de votre organisation. Pour restreindre et contrôler les personnes autorisées à utiliser l’application, vous pouvez créer et affecter une stratégie d’autorisations d’application. Pour en savoir plus, voir <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">gérer les stratégies d’autorisation d’applications dans Microsoft teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Épingler et installer l’application pour détecter les utilisateurs

Par défaut, pour que les utilisateurs puissent trouver l’application, ils doivent accéder au magasin d’applications de votre organisation et rechercher celles-ci. Pour permettre aux utilisateurs d’accéder facilement à l’application, vous pouvez épingler l’application à la barre de l’application dans Teams. Pour ce faire, créez une stratégie de configuration d’application et attribuez-la à des utilisateurs. Pour en savoir plus, voir <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">gérer les stratégies de configuration des applications dans Microsoft teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Effectuer une recherche dans le journal d’audit pour les événements d’application teams

Vous pouvez effectuer une recherche dans le journal d’audit pour afficher l’activité des applications teams au sein de votre organisation. Pour en savoir plus sur la façon d’effectuer une recherche dans le journal d’audit et d’afficher la liste des activités d’équipe qui sont enregistrées dans le journal d’audit, voir <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">Rechercher des événements dans le journal d’audit dans teams</a>.

Pour pouvoir effectuer une recherche dans le journal d’audit, vous devez d’abord activer l’audit dans le <a href="https://protection.office.com" target="_blank">Centre de sécurité & conformité</a>. Pour plus d’informations, voir <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">activer ou désactiver la recherche dans le journal d’audit</a>. Gardez à l’esprit que les données d’audit sont uniquement disponibles à partir du point d’activation de l’audit.

## <a name="discover-and-adopt"></a>Découvrir et adopter

Les utilisateurs disposant de droits d’accès à l’application peuvent les trouver dans le magasin d’applications de votre organisation. Accédez au **nom conçu pour le *nom de votre organisation* ** dans la page applications pour trouver les applications personnalisées de votre organisation.

![Capture d’écran de la page applications affichant l’application publiée ](media/custom-app-lifecycle-discovery.png)

Si vous avez créé et affecté une stratégie de configuration de l’application, l’application est épinglée à la barre de l’application dans teams pour faciliter l’accès aux utilisateurs qui ont reçu la stratégie.

## <a name="update"></a>Mettre à jour

Pour mettre à jour une application, les développeurs doivent continuer à suivre les étapes des sections [développer](#develop) et [valider](#validate) .

Vous pouvez mettre à jour l’application sur la page gérer les applications dans le centre d’administration Microsoft Teams. Pour ce faire, dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **applications d’équipe**  >  **gérer les applications**. Cliquez sur le nom de l’application, puis sur **mettre à jour**. Cela a pour effet de remplacer l’application existante, et toutes les stratégies d’autorisation et les stratégies de configuration de l’application sont appliquées pour l’application mise à jour.

### <a name="end-user-update-experience"></a>Mise à jour des utilisateurs finaux

Dans la plupart des cas, une fois que vous avez effectué une mise à jour de l’application, la nouvelle version s’affiche automatiquement pour les utilisateurs finaux. Il y a toutefois des mises à jour du <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">manifeste Microsoft teams</a> qui nécessitent l’acceptation de l’utilisateur :

* Un bot a été ajouté ou supprimé
* Modification de la propriété « botId » d’une bot existante
* Modification de la propriété « isNotificationOnly » d’une bot existante
* La propriété « supportsFiles » du bot a changé
* Ajout ou suppression d’une extension de messagerie
* Un nouveau connecteur a été ajouté.
* Un nouvel onglet statique a été ajouté.
* Un nouvel onglet configurable a été ajouté.
* Propriétés dans « webApplicationInfo » modifiées

![Capture d’écran de la liste des applications, avec les applications pour lesquelles une nouvelle version est disponible](media/manage-your-custom-apps-update1.png)

![Capture d’écran de l’option de mise à niveau pour une application](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Voir aussi

- [Publier une application personnalisée soumise par le biais de l’API de soumission d’applications teams](submit-approve-custom-apps.md)
- [Gérer vos applications dans le centre d’administration Microsoft teams](manage-apps.md)
- [Gérer les stratégies d’application personnalisée et les paramètres dans Teams](teams-custom-app-policies-and-settings.md)
- [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
- [Gérer les stratégies de mise en application dans Teams](teams-app-setup-policies.md)
