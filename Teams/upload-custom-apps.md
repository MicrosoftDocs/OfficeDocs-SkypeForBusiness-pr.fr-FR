---
title: Charger vos applications personnalisées dans le Centre d’administration Microsoft Teams
author: guptaashish
ms.author: guptaashish
manager: prkosh
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
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez comment charger vos applications personnalisées dans l’App Store de votre organisation dans le Centre d’administration Microsoft Teams.
ms.openlocfilehash: 5ef5992e01b5de4e2f4feaed51b50e2d0f16c0d8
ms.sourcegitcommit: 4be2a5db44972b35bdde5752eea0d74cf831607a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/06/2022
ms.locfileid: "66642759"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Publier une application personnalisée en chargeant un package d’application

> [!NOTE]
> Lorsque vous publiez une application Teams personnalisée, elle est disponible pour les utilisateurs de l’App Store de votre organisation. Il existe deux façons de publier une application personnalisée et la façon dont vous l’utilisez dépend de la façon dont vous obtenez l’application. **Cet article se concentre sur la façon de publier une application personnalisée en chargeant un package d’application (au format .zip) qu’un développeur vous envoie**. L’autre méthode, l’approbation d’une application personnalisée, est utilisée lorsqu’un développeur envoie une application directement à la page [Gérer les applications](manage-apps.md) via l’API De soumission d’applications Teams. Pour en savoir plus sur cette méthode, consultez [Publier une application personnalisée envoyée via l’API de soumission d’application Teams](submit-approve-custom-apps.md).

Cet article fournit des conseils de bout en bout sur la façon de faire passer votre application Teams du développement au déploiement en passant par la découverte. Ces conseils se concentrent sur les aspects Teams de l’application et sont destinés aux administrateurs et aux professionnels de l’informatique. Pour plus d’informations sur le développement d’applications Teams, consultez la [documentation du développeur Teams](/microsoftteams/platform/).

![Vue d’ensemble de votre application du développement au déploiement.](media/upload-custom-apps.png)

## <a name="create-your-app"></a>Créer votre application

La plateforme de développement Microsoft Teams permet aux développeurs d’intégrer facilement vos propres applications et services afin d’améliorer la productivité, de prendre des décisions plus rapidement et de créer une collaboration autour du contenu et des workflows existants. Les applications basées sur la plateforme Teams sont des ponts entre le client Teams et vos services et flux de travail, en les intégrant directement dans le contexte de votre plateforme de collaboration. Pour plus d’informations, consultez la [documentation du développeur Teams](/microsoftteams/platform/).

## <a name="validate"></a>Valider

### <a name="get-the-app-package"></a>Obtenir le package d’application

Lorsque l’application est prête à être utilisée en production, le développeur doit produire un package d’application. Ils peuvent utiliser [App Studio](/microsoftteams/platform/concepts/build-and-test/app-studio-overview). Ils vous enverront le fichier au format .zip.

Toutes les applications du Magasin Teams réussissent une [validation d’application](overview-of-app-validation.md) obligatoire pour se conformer aux normes de qualité et de sécurité du magasin mondial d’applications Teams. En outre, Microsoft encourage vivement les développeurs d’applications à participer à un programme facultatif de [conformité des applications](overview-of-app-certification.md) qui indique des contrôles de conformité, de sécurité et de confidentialité améliorés. Pour plus d’informations, consultez [les instructions de validation des applications Teams](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/teams-store-validation-guidelines).

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Autoriser les utilisateurs approuvés à charger des applications personnalisées

Pour vérifier que l’application fonctionne correctement dans votre locataire de production, vous devez autoriser vous-même et/ou les utilisateurs approuvés à charger des applications personnalisées dans le locataire de production. Pour ce faire, vous utilisez des [stratégies d’installation](teams-app-setup-policies.md) d’application.

> [!NOTE]
> Si vous n’êtes pas à l’aise avec le chargement de l’application sur votre locataire de production à des fins de validation, même pour vous-même ou les utilisateurs approuvés, vous pouvez ignorer cette étape et suivre les étapes décrites dans les sections [Charger](#upload) et [configurer et gérer](#set-up-and-manage) pour publier l’application non validée dans l’App Store de votre organisation. Ensuite, limitez l’accès à cette application uniquement à vous-même et aux utilisateurs de confiance. Ces utilisateurs peuvent ensuite obtenir l’application à partir de l’App Store de votre organisation pour effectuer la validation. Une fois l’application validée, utilisez les mêmes stratégies d’autorisation pour ouvrir l’accès et déployer l’application pour une utilisation en production.

Pour permettre aux utilisateurs approuvés de charger des applications personnalisées, procédez comme suit :

1. Activez le paramètre **Autoriser l’interaction avec les applications personnalisées** à l’échelle de l’organisation. Pour ce faire :

    1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à Applications **Teams** > **Gérer les applications**, puis cliquez sur **Paramètres d’application à l’échelle de l’organisation**.
    
    2. Sous **Applications personnalisées**, **activez Autoriser l’interaction avec les applications personnalisées**, puis cliquez sur **Enregistrer**.
    
1. Désactivez le paramètre **Charger des applications personnalisées** dans la stratégie d’installation d’application globale. Pour ce faire :

    1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **stratégies d’installation** des **applications** >  Teams, puis cliquez sur la stratégie **globale (par défaut à l’échelle de l’organisation**).
    
    2. Désactivez **Télécharger des applications personnalisées**, puis cliquez sur **Enregistrer**.
    
1. Créez une stratégie d’installation d’application qui permet de charger des applications personnalisées et de l’affecter à votre ensemble d’utilisateurs approuvés. Pour ce faire :

    1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **stratégies d’installation** des **applications** >  Teams, puis cliquez sur **Ajouter**. Donnez un nom et une description à la nouvelle stratégie, **activez Charger des applications personnalisées**, puis cliquez sur **Enregistrer**.
    
    2. Sélectionnez la nouvelle stratégie que vous avez créée, puis cliquez sur **Gérer les utilisateurs**. Recherchez un utilisateur, cliquez sur **Ajouter**, puis cliquez sur **Appliquer**. Répétez cette étape pour affecter la stratégie à tous vos utilisateurs approuvés.

       ![Capture d’écran de la page « Ajouter une stratégie d’installation d’application »](media/manage-your-lob-apps-new-app-setup-policy.png)

Ces utilisateurs peuvent maintenant charger le manifeste de l’application pour vérifier que l’application fonctionne correctement dans le locataire de production.

## <a name="upload"></a>Télécharger

Pour mettre l’application à la disposition des utilisateurs de l’App Store de votre organisation, chargez l’application.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à Applications **Teams** > **[Gérer les applications](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Sélectionnez **Charger**, cliquez sur **Charger**, sélectionnez le package d’application que vous avez reçu du développeur, puis **sélectionnez Ouvrir**.

   ![Capture d’écran du chargement d’une application dans le Centre d’administration.](media/manage-your-lob-apps-upload-new-app.png)

## <a name="set-up-and-manage"></a>Configurer et gérer

### <a name="control-access-to-the-app"></a>Contrôler l’accès à l’application

Par défaut, tous les utilisateurs de votre organisation peuvent accéder à l’application dans l’App Store de votre organisation. Pour restreindre et contrôler qui a l’autorisation d’utiliser l’application, vous pouvez créer et attribuer une stratégie d’autorisation d’application. Pour plus d’informations, consultez [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md).

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Épingler et installer l’application pour que les utilisateurs découvrent

Par défaut, pour que les utilisateurs trouvent l’application, ils doivent accéder à l’App Store de votre organisation et la rechercher. Pour permettre aux utilisateurs d’accéder facilement à l’application, vous pouvez épingler l’application à la barre de l’application dans Teams. Pour ce faire, créez une stratégie d’installation d’application et attribuez-la aux utilisateurs. Pour plus d’informations, consultez l’article [Gérer les stratégies et paramètres d’application personnalisés dans Teams](teams-app-setup-policies.md).

### <a name="search-the-audit-log-for-teams-app-events"></a>Rechercher des événements d’application Teams dans le journal d’audit

Vous pouvez effectuer une recherche dans le journal d’audit pour afficher l’activité des applications Teams dans votre organisation. Pour en savoir plus sur l’audit des activités Teams, consultez [la recherche d’événements dans Teams dans le journal d’audit](audit-app-management-activities.md).

Pour effectuer une recherche dans le journal d’audit, vous devez au préalable activer la fonctionnalité d’audit dans le [Centre de sécurité et de conformité](https://sip.protection.office.com/homepage). Si vous souhaitez en savoir plus, veuillez consulter [Activer ou désactiver la recherche dans le journal d'audit](/microsoft-365/compliance/turn-audit-log-search-on-or-off). N’oubliez pas que les données d’audit ne sont disponibles qu’à partir du moment où vous avez activé l’audit.

## <a name="discover-and-adopt"></a>Découvrir et adopter

Les utilisateurs finaux qui disposent d’autorisations sur l’application peuvent la trouver dans l’App Store de votre organisation. Accédez à **Built for *Your Organization Name*** dans la page Applications pour rechercher les applications personnalisées de votre organisation.

:::image type="content" source="media/custom-app-lifecycle-discovery.png" alt-text="Capture d’écran du magasin Teams montrant l’application personnalisée publiée pour l’organisation" lightbox="media/custom-app-lifecycle-discovery.png":::

Si vous avez créé et affecté une stratégie d’installation d’application, l’application est épinglée à la barre des applications dans Teams pour faciliter l’accès aux utilisateurs auxquels la stratégie a été attribuée.

## <a name="update"></a>Mettre à jour

Pour mettre à jour une application, les développeurs suivent les étapes décrites dans les sections [Créer votre application](#create-your-app) et [Valider](#validate) .

Vous pouvez mettre à jour l’application sur la page Gérer les applications dans le Centre d’administration Microsoft Teams. Pour ce faire, dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez à Teams **Apps** > **Manage apps**. Cliquez sur le nom de l’application, puis sur **Mettre à jour**. Cette opération remplace l’application existante, et toutes les stratégies d’autorisation d’application et les stratégies d’installation d’application restent appliquées pour l’application mise à jour.

### <a name="end-user-update-experience"></a>Expérience de mise à jour de l’utilisateur final

Dans la plupart des cas, une fois que vous avez terminé une mise à jour d’application, la nouvelle version s’affiche automatiquement pour les utilisateurs finaux. Pour plus d’informations, consultez [l’expérience de mise à jour de l’utilisateur final](apps-update-experience.md).

## <a name="related-topics"></a>Sujets associés

* [Publier une application personnalisée envoyée via l’API de soumission d’application Teams](submit-approve-custom-apps.md)
* [Gérer vos applications dans le Centre d’administration Microsoft Teams](manage-apps.md)
* [Gérer les stratégies d’application personnalisée et les paramètres dans Teams](teams-custom-app-policies-and-settings.md)
* [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
* [Gérer les stratégies de mise en application dans Teams](teams-app-setup-policies.md)
