---
title: Télécharger vos applications personnalisées dans le Centre Microsoft Teams’administration
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
description: Découvrez comment télécharger vos applications personnalisées dans le magasin d’applications de votre organisation dans le Microsoft Teams d’administration.
ms.openlocfilehash: f9cbbfb60b2bb93cb3f687e6da8c6595f5cc185b
ms.sourcegitcommit: de6eb0478a79e178c5d02cdab8cca44a88beb853
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2022
ms.locfileid: "63070183"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Publier une application personnalisée en chargeant un package d’application

> [!NOTE]
> Lorsque vous publiez une application Teams personnalisée, elle est disponible pour les utilisateurs dans le magasin d’applications de votre organisation. Il existe deux façons de publier une application personnalisée et la façon dont vous l’utilisez dépend de la façon dont vous l’obtenez. **Cet article explique comment publier** une application personnalisée en chargeant un package d’application (au format .zip) qu’un développeur vous envoie. L’autre méthode, l’approbation d’une application personnalisée, est utilisée lorsqu’un développeur envoie une application directement à <a href="/microsoftteams/manage-apps" target="_blank">la page Gérer</a> les applications via l’API Teams App Submission. Pour en savoir plus sur cette méthode, voir <a href="/microsoftteams/submit-approve-custom-apps" target="_blank">Publier une application personnalisée envoyée via l’API de soumission Teams’application</a>.

Cet article fournit des instructions de bout en bout sur la façon d’orienter votre application Teams du développement au déploiement jusqu’à la découverte. Ces conseils se concentrent sur Teams aspects de l’application et sont destinés aux administrateurs et professionnels de l’informatique. Pour plus d’informations sur le développement Teams applications, voir la <a href="/microsoftteams/platform" target="_blank">documentation Teams développeur.</a>

![Vue d’ensemble de votre application, du développement au déploiement.](media/upload-custom-apps.png)

## <a name="develop"></a>Développer

### <a name="create-your-app"></a>Créer votre application

La plateforme Microsoft Teams développeur permet aux développeurs d’intégrer facilement vos propres applications et services afin d’améliorer la productivité, de prendre des décisions plus rapidement et de créer une collaboration autour du contenu et des flux de travail existants. Les applications conçues sur la plateforme Teams sont des ponts entre le client Teams et vos services et flux de travail, ce qui les place directement dans le contexte de votre plateforme de collaboration. Pour plus d’informations, voir la documentation <a href="/microsoftteams/platform" target="_blank">Teams développeur</a>.

## <a name="validate"></a>Validate

### <a name="get-the-app-package"></a>Obtenir le package d’application

Lorsque l’application est prête à être utilisé en production, le développeur doit produire un package d’application. Ils peuvent utiliser <a href="/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> pour cela. Ils vous enverront le fichier au .zip format.

Microsoft <a href="/microsoftteams/platform/publishing/office-store-approval" target="_blank">s’appuie sur ces directives</a> pour s’assurer que les applications sont conformes aux normes de qualité et de sécurité du Teams apps store.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Autoriser les utilisateurs de confiance à télécharger des applications personnalisées

Pour vérifier que l’application fonctionne correctement dans votre client de production, vous devez vous autoriser, ainsi que/ou les utilisateurs de confiance, à télécharger des applications personnalisées dans le client de production. Pour ce faire <a href="/microsoftteams/teams-app-setup-policies" target="_blank">, vous devez</a> utiliser des stratégies de configuration d’application.

> [!NOTE]
> Si vous ne souhaitez pas télécharger l’application dans votre client de production à des fins de validation, même pour vous-même ou des utilisateurs de confiance, vous pouvez ignorer cette étape et suivre les étapes du [Télécharger](#upload) et configurer et gérer [des sections](#set-up-and-manage) pour publier l’application nonvalidée dans le magasin d’applications de votre organisation. Ensuite, limitez l’accès à cette application uniquement à vous-même et aux utilisateurs de confiance. Ces utilisateurs peuvent ensuite obtenir l’application à partir du magasin d’applications de votre organisation pour effectuer une validation. Une fois l’application validée, utilisez les mêmes stratégies d’autorisation pour ouvrir l’accès à l’application et la déployer en production.

Pour autoriser les utilisateurs de confiance à télécharger des applications personnalisées, suivez ces étapes :

1. Activer le paramètre **d’application Autoriser l’interaction avec des applications** personnalisées à l’échelle de l’organisation. Pour ce faire :
    1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, allez dans **Teams** **applicationsManage** > , puis cliquez sur Paramètres de l’application à **l’échelle de l’organisation**.
    2. Sous **Applications personnalisées**, activer **l’application Autoriser l’interaction avec** les applications personnalisées, puis cliquez sur **Enregistrer**.
2. Désactiver le paramètre **Télécharger d’applications personnalisées** dans la stratégie de configuration globale de l’application. Pour ce faire :
    1. Dans le navigation gauche du Centre d’administration Microsoft Teams, allez dans **Teams** **appsSetup** >  policies, puis cliquez sur la stratégie **Global (** à l’échelle de l’organisation par défaut).
    2. Désactiver Télécharger **applications personnalisées**, puis cliquez sur **Enregistrer**.
3. Créez une stratégie de configuration d’application qui permet de télécharger des applications personnalisées et de les affecter à votre ensemble d’utilisateurs de confiance. Pour ce faire :
    1. Dans le panneau de navigation gauche du Microsoft Teams d’administration, cliquez sur **Teams d’applicationSetup** > , puis cliquez sur **Ajouter**. Donnez un nom et une description à la nouvelle stratégie, Télécharger applications personnalisées **, puis** cliquez sur **Enregistrer**.
    2. Sélectionnez la nouvelle stratégie que vous avez créée, puis cliquez sur **Gérer les utilisateurs**. Recherchez un utilisateur, cliquez **sur Ajouter**, puis sur **Appliquer**. Répétez cette étape pour affecter la stratégie à tous vos utilisateurs de confiance.

        ![Capture d’écran de la page « Ajouter une stratégie de configuration d’application »](media/manage-your-lob-apps-new-app-setup-policy.png)

    Ces utilisateurs peuvent désormais télécharger le manifeste de l’application pour vérifier que l’application fonctionne correctement dans le client de production.

## <a name="upload"></a>Télécharger

Pour mettre l’application à la disposition des utilisateurs dans le magasin d’applications de votre organisation, téléchargez l’application. Pour ce faire, vous pouvez utiliser la page <a href="/microsoftteams/manage-apps" target="_blank">Gérer les</a> applications du Centre Microsoft Teams’administration.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**.
2. **Sélectionnez Télécharger**, cliquez **Télécharger**, sélectionnez le package d’application que vous avez reçu du développeur, puis **sélectionnez Ouvrir**.

   ![Capture d’écran du chargement d’une application dans le Centre d’administration.](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Configurer et gérer

### <a name="control-access-to-the-app"></a>Contrôler l’accès à l’application

Par défaut, tous les utilisateurs de votre organisation peuvent accéder à l’application dans le magasin d’applications de votre organisation. Pour restreindre et contrôler les personnes autorisées à utiliser l’application, vous pouvez créer et affecter une stratégie d’autorisation d’application. Pour plus d’informations, consultez <a href="/microsoftteams/teams-app-permission-policies" target="_blank">Gérer les stratégies d’autorisation d’application dans Teams</a>.

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Épingler et installer l’application pour les utilisateurs

Par défaut, pour que les utilisateurs trouvent l’application qu’ils doivent trouver, ils doivent se rendre dans le magasin d’applications de votre organisation et la parcourir ou la rechercher. Pour faciliter l’accès des utilisateurs à l’application, vous pouvez épingler l’application à la barre d’application dans Teams. Pour ce faire, créez une stratégie de configuration d’application et attribuez-la aux utilisateurs. Pour plus d’informations, consultez l’article <a href="/microsoftteams/teams-app-setup-policies" target="_blank">Gérer les stratégies et paramètres d’application personnalisés dans Teams</a>.

### <a name="search-the-audit-log-for-teams-app-events"></a>Rechercher des événements d’application Teams dans le journal d’audit

Vous pouvez effectuer des recherches dans le journal d’audit Teams l’activité des applications dans votre organisation. Pour en savoir plus sur la recherche dans le journal d’audit et la liste des activités Teams enregistrées dans le journal d’audit, voir Rechercher des événements dans le journal <a href="/microsoftteams/audit-log-events" target="_blank">d’audit dans Teams</a>.

Pour effectuer une recherche dans le journal d’audit, vous devez au préalable activer la fonctionnalité d’audit dans le <a href="https://protection.office.com" target="_blank">Centre de sécurité et de conformité</a>. Si vous souhaitez en savoir plus, veuillez consulter <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">Activer ou désactiver la recherche dans le journal d'audit</a>. N’oubliez pas que les données d’audit ne sont disponibles qu’à partir du moment où vous avez activé l’audit.

## <a name="discover-and-adopt"></a>Découvrir et adopter

Les utilisateurs qui ont des autorisations sur l’application peuvent la trouver dans le magasin d’applications de votre organisation. Dans la page Applications, allez à Built **for *Your Organization Name*** (Conçu pour le nom de votre organisation) pour rechercher les applications personnalisées de votre organisation.

![Capture d’écran de la page Applications affichant l’application publiée.](media/custom-app-lifecycle-discovery.png)

Si vous avez créé et attribué une stratégie de configuration d’application, l’application est épinglée à la barre d’application dans Teams pour faciliter l’accès aux utilisateurs à qui la stratégie a été attribuée.

## <a name="update"></a>Mettre à jour

Pour mettre à jour une application, les développeurs doivent continuer à suivre les [](#develop) étapes [des sections](#validate) Développer et valider.

Vous pouvez mettre à jour l’application dans la page Gérer les applications du Microsoft Teams d’administration. Pour ce faire, dans le navigation gauche du Microsoft Teams d’administration, Teams **applications** **AppsManage** > . Cliquez sur le nom de l’application, puis sur **Mettre à jour**. Cette faisant, vous remplacez l’application existante, et toutes les stratégies d’autorisation d’application et toutes les stratégies de configuration d’application demeurent appliquées pour l’application mise à jour.

### <a name="end-user-update-experience"></a>Expérience de mise à jour des utilisateurs finux

Dans la plupart des cas, une fois que vous avez terminé une mise à jour d’application, la nouvelle version s’affiche automatiquement pour les utilisateurs finaux. Toutefois, certaines mises à jour du manifeste <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams</a> nécessitent l’acceptation des utilisateurs :

* Un robot a été ajouté ou supprimé
* La propriété « botId » d’un robot existant a été modifiée
* La propriété « isNotificationOnly » d’un robot existant a été modifiée
* La propriété « SupportsFiles » du bot a été modifiée
* Une extension de messagerie a été ajoutée ou supprimée
* Un nouveau connecteur a été ajouté
* Un nouvel onglet statique a été ajouté
* Un nouvel onglet configurable a été ajouté
* Propriétés dans « webApplicationInfo » modifiées

![Capture d’écran de la liste des applications, montrant les applications dont la version est nouvelle disponible.](media/manage-your-custom-apps-update1.png)

![Capture d’écran de l’option de mise à niveau pour une application.](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Sujets associés

- [Publier une application personnalisée envoyée via l’API Teams App Submission](submit-approve-custom-apps.md)
- [Gérer vos applications dans le Centre Microsoft Teams’administration](manage-apps.md)
- [Gérer les stratégies d’application personnalisée et les paramètres dans Teams](teams-custom-app-policies-and-settings.md)
- [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
- [Gérer les stratégies de mise en application dans Teams](teams-app-setup-policies.md)
