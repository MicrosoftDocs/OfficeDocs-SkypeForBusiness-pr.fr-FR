---
title: Télécharger vos applications personnalisées dans le Centre d’administration Microsoft Teams
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
description: Découvrez comment télécharger vos applications personnalisées dans le magasin d’applications de votre organisation dans le Centre d’administration Microsoft Teams.
ms.openlocfilehash: f1b5267fe1003d69c0d91349f5b6bc425df2b038
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831164"
---
# <a name="publish-a-custom-app-by-uploading-an-app-package"></a>Publier une application personnalisée en chargeant un package d’application

> [!NOTE]
> Lorsque vous publiez une application Teams personnalisée, elle est disponible pour les utilisateurs dans le magasin d’applications de votre organisation. Il existe deux façons de publier une application personnalisée et la façon dont vous l’utilisez dépend de la façon dont vous l’obtenez. Cet article explique comment publier une application personnalisée en téléchargeant un package d’application **(au format .zip) qu’un** développeur vous envoie. L’autre méthode, l’approbation d’une application personnalisée, est utilisée lorsqu’un développeur envoie une application directement à la <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">page</a> Gérer les applications via l’API Soumission d’application Teams. Pour en savoir plus sur cette méthode, voir Publier une application personnalisée envoyée <a href="https://docs.microsoft.com/microsoftteams/submit-approve-custom-apps" target="_blank">via l’API De soumission d’application Teams.</a>

Cet article fournit des conseils de bout en bout sur la façon d’aller du développement à la découverte de votre application Teams. Ces conseils se concentrent sur les aspects Teams de l’application et sont destinés aux administrateurs et professionnels de l’informatique. Pour plus d’informations sur le développement d’applications Teams, consultez <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">la documentation des développeurs Teams.</a>

![Vue d’ensemble de votre application, du développement au déploiement](media/upload-custom-apps.png)

## <a name="develop"></a>Développer

### <a name="create-your-app"></a>Créer votre application

La plateforme de développement Microsoft Teams permet aux développeurs d’intégrer facilement vos propres applications et services afin d’améliorer la productivité, de prendre des décisions plus rapidement et de créer une collaboration autour du contenu existant et des flux de travail. Les applications conçues sur la plateforme Teams sont des ponts entre le client Teams et vos services et flux de travail, ce qui les place directement dans le contexte de votre plateforme de collaboration. Pour plus d’informations, voir la <a href="https://docs.microsoft.com/microsoftteams/platform" target="_blank">documentation du développeur teams.</a>

## <a name="validate"></a>Validate

### <a name="get-the-app-package"></a>Obtenir le package d’application

Lorsque l’application est prête à être utilisé en production, le développeur doit produire un package d’application. Ils peuvent utiliser <a href="https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio" target="_blank">App Studio</a> pour cela. Ils vous enverront le fichier au format .zip.

Microsoft <a href="https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-approval" target="_blank">s’appuie sur ces directives</a> pour s’assurer que les applications sont conformes aux normes de qualité et de sécurité du magasin d’applications Teams à l’échelle mondiale.

### <a name="allow-trusted-users-to-upload-custom-apps"></a>Autoriser les utilisateurs de confiance à télécharger des applications personnalisées

Pour vérifier que l’application fonctionne correctement dans votre client de production, vous devez vous autoriser, ainsi que/ou les utilisateurs de confiance, à télécharger des applications personnalisées dans le client de production. Pour ce <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">faire, vous devez</a> utiliser des stratégies de configuration d’application.

> [!NOTE]
> Si vous ne parvient pas à télécharger l’application dans votre client de production à des fins de [](#upload) validation, même pour vous-même ou des utilisateurs de confiance, vous pouvez ignorer cette étape et suivre les étapes de la section Télécharger et configurer et gérer pour publier l’application nonvalidée dans le magasin d’applications de votre organisation. [](#set-up-and-manage) Ensuite, limitez l’accès à cette application uniquement à vous-même et aux utilisateurs de confiance. Ces utilisateurs peuvent ensuite obtenir l’application à partir du magasin d’applications de votre organisation pour effectuer la validation. Une fois l’application validée, utilisez les mêmes stratégies d’autorisation pour ouvrir l’accès à l’application et la déployer en production.

Pour autoriser les utilisateurs de confiance à télécharger des applications personnalisées, suivez ces étapes :

1. Activer le paramètre **d’application Autoriser l’interaction avec** des applications personnalisées à l’échelle de l’organisation. Pour ce faire :
    1. Dans le navigation gauche du Centre d’administration Microsoft Teams, allez aux applications **Teams** Gérer les applications, puis cliquez sur Paramètres de l’application à  >   **l’échelle de l’organisation.**
    2. Sous **Applications personnalisées,** activer Autoriser **l’interaction avec** les applications personnalisées, puis cliquez sur **Enregistrer.**
2. Désactiver le paramètre **Télécharger des applications personnalisées** dans la stratégie de configuration globale de l’application. Pour ce faire :
    1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez aux stratégies de configuration des applications **Teams,** puis cliquez sur la stratégie Globale (à l’échelle de  >   **l’organisation par** défaut).
    2. Désactiver télécharger **les applications personnalisées,** puis cliquer sur **Enregistrer.**
3. Créez une stratégie de configuration d’application qui permet de télécharger des applications personnalisées et de les affecter à votre ensemble d’utilisateurs de confiance. Pour ce faire :
    1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, consultez les stratégies de configuration des applications **Teams,** puis  >  cliquez sur **Ajouter.** Donnez un nom et une description à la nouvelle stratégie, activer **Télécharger les** applications personnalisées, puis cliquez sur **Enregistrer.**
    2. Sélectionnez la nouvelle stratégie que vous avez créée, puis cliquez sur **Gérer les utilisateurs.** Recherchez un utilisateur, cliquez **sur Ajouter,** puis sur **Appliquer.** Répétez cette étape pour affecter la stratégie à tous vos utilisateurs de confiance.

        ![Capture d’écran de la page « Ajouter une stratégie de configuration d’application »](media/manage-your-lob-apps-new-app-setup-policy.png)

    Ces utilisateurs peuvent désormais télécharger le manifeste de l’application pour vérifier que l’application fonctionne correctement dans le client de production.

## <a name="upload"></a>Charger

Pour mettre l’application à la disposition des utilisateurs dans le magasin d’applications de votre organisation, téléchargez l’application. Pour ce faire, vous pouvez le faire sur la page <a href="https://docs.microsoft.com/microsoftteams/manage-apps" target="_blank">Gérer les</a> applications du Centre d’administration Microsoft Teams.

1. Dans le panneau de navigation gauche du Centre d’administration Microsoft Teams, allez à **l’application Teams** Gérer  >  **les applications.**
2. Cliquez **sur** Charger, **sélectionnez un fichier,** puis sélectionnez le package d’application que vous avez reçu du développeur.

   ![Capture d’écran du chargement d’une application dans le Centre d’administration](media/manage-your-lob-apps-upload-new-app.png) 

## <a name="set-up-and-manage"></a>Configurer et gérer

### <a name="control-access-to-the-app"></a>Contrôler l’accès à l’application

Par défaut, tous les utilisateurs de votre organisation peuvent accéder à l’application dans le magasin d’applications de votre organisation. Pour restreindre et contrôler les personnes autorisées à utiliser l’application, vous pouvez créer et affecter une stratégie d’autorisation d’application. Pour en savoir plus, consultez <a href="https://docs.microsoft.com/microsoftteams/teams-app-permission-policies" target="_blank">Gérer les stratégies d’autorisation d’application dans Teams.</a>

### <a name="pin-and-install-the-app-for-users-to-discover"></a>Épingler et installer l’application pour les utilisateurs

Par défaut, pour que les utilisateurs trouvent l’application qu’ils doivent trouver, accédez au magasin d’applications de votre organisation et parcourez-la ou recherchez-la. Pour faciliter l’accès des utilisateurs à l’application, vous pouvez épingler l’application à la barre de l’application dans Teams. Pour ce faire, créez une stratégie de configuration d’application et affectez-la aux utilisateurs. Pour en savoir plus, consultez <a href="https://docs.microsoft.com/microsoftteams/teams-app-setup-policies" target="_blank">Gérer les stratégies de configuration d’application dans Teams.</a>

### <a name="search-the-audit-log-for-teams-app-events"></a>Rechercher des événements d’application Teams dans le journal d’audit

Vous pouvez effectuer des recherches dans le journal d’audit pour afficher l’activité des applications Teams dans votre organisation. Pour en savoir plus sur la recherche dans le journal d’audit et l’accès à la liste des activités Teams enregistrées dans le journal d’audit, consultez Rechercher des événements dans Teams dans le journal <a href="https://docs.microsoft.com/microsoftteams/audit-log-events" target="_blank">d’audit.</a>

Avant d’effectuer une recherche dans le journal d’audit, vous devez activer l’audit dans le Centre <a href="https://protection.office.com" target="_blank">& conformité.</a> Pour en savoir plus, voir Activer ou désactiver la recherche dans le <a href="https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014" target="_blank">journal d’audit.</a> Gardez à l’esprit que les données d’audit sont uniquement disponibles à partir du moment où vous avez désactivé l’audit.

## <a name="discover-and-adopt"></a>Découvrir et adopter

Les utilisateurs qui ont des autorisations sur l’application peuvent la trouver dans le magasin d’applications de votre organisation. Dans la page Applications, allez à Built **for *Your Organization Name*** (Conçu pour le nom de votre organisation) pour rechercher les applications personnalisées de votre organisation.

![Capture d’écran de la page Applications affichant l’application publiée ](media/custom-app-lifecycle-discovery.png)

Si vous avez créé et attribué une stratégie de configuration d’application, l’application est épinglée à la barre d’application dans Teams pour faciliter l’accès aux utilisateurs à qui la stratégie a été attribuée.

## <a name="update"></a>Mettre à jour

Pour mettre à jour une application, les [](#develop) développeurs doivent continuer à suivre les étapes des [sections](#validate) Développer et valider.

Vous pouvez mettre à jour l’application dans la page Gérer les applications du Centre d’administration Microsoft Teams. Pour ce faire, dans le navigation gauche du Centre d’administration Microsoft Teams, allez dans les applications **Teams**  >  **Gérer les applications.** Cliquez sur le nom de l’application, puis sur **Mettre à jour.** Cette faisant, vous remplacez l’application existante, et toutes les stratégies d’autorisation d’application et toutes les stratégies de configuration d’application demeurent appliquées pour l’application mise à jour.

### <a name="end-user-update-experience"></a>Expérience de mise à jour des utilisateurs finux

Dans la plupart des cas, une fois que vous avez terminé la mise à jour d’une application, la nouvelle version s’affiche automatiquement pour les utilisateurs finaux. Toutefois, certaines mises à jour du manifeste <a href="https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">de Microsoft Teams</a> nécessitent l’acceptation des utilisateurs :

* Un robot a été ajouté ou supprimé
* La propriété « botId » d’un robot existant a été modifiée
* La propriété « isNotificationOnly » d’un robot existant a été modifiée
* La propriété « SupportsFiles » du bot a été modifiée
* Une extension de messagerie a été ajoutée ou supprimée
* Un nouveau connecteur a été ajouté
* Un nouvel onglet statique a été ajouté
* Un nouvel onglet configurable a été ajouté
* Propriétés dans « webApplicationInfo » modifiées

![Capture d’écran de la liste des applications, montrant les applications dont la nouvelle version est disponible](media/manage-your-custom-apps-update1.png)

![Capture d’écran de l’option de mise à niveau pour une application](media/manage-your-custom-apps-update2.png)

## <a name="related-topics"></a>Sujets associés

- [Publier une application personnalisée envoyée via l’API De soumission d’application Teams](submit-approve-custom-apps.md)
- [Gérer vos applications dans le Centre d’administration Microsoft Teams](manage-apps.md)
- [Gérer les stratégies d’application personnalisée et les paramètres dans Teams](teams-custom-app-policies-and-settings.md)
- [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
- [Gérer les stratégies de mise en application dans Teams](teams-app-setup-policies.md)
